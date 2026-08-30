# TB3 H100 租用与提交说明

Last updated: 2026-08-29

这份说明只管两件事：

1. 什么时候需要租 H100；
2. TB3 的正式提交 / 上传流程怎么走。

## 什么时候租 H100

只有当任务说明里明确要求 H100，或者任务的验证器/README 明确写了 H100、sm_90a、单卡 H100、或本地路径没有 GPU 分配能力时，才租。

不要为了“先试试”在本地 Docker-only 路径上硬烧时间。TB3 里这类题通常应该直接走云端 H100。

### 先看这些文件

- `task.toml`
- `instruction.md`
- `README.md`
- `tests/` 里的 verifier 说明

如果这些文件里写了 H100，就按 H100 处理。

## 先做什么，再正式跑

建议顺序：

1. 读任务文件，确认是否真需要 H100。
2. 先做 K=1 探针，确认环境、桥接和 verifier 链路可用。
3. 探针通过后，再开正式 K5。

不要一上来就 K5 然后把失败批次当成绩。

## TB3 正式 K5 的合格标准

一个任务只有满足下面全部条件，才算正式候选：

- 5 completed
- 0 errored
- 0 running
- 0 pending
- 5 个 reward 都是 1.0
- `result.json` 和 trajectory 完整保留

`Harbor returncode=0`、`passive supervisor` 启动、`public smoke`、或者只跑通了部分 trial，都不算完成。

## 推荐的 Harbor 启动模板

以 Harbor 当前 help 为准，常用参数是：

- `-d terminal-bench/terminal-bench@3.0.0`
- `-i <task_name>` 或 `-t <task_name>`
- `-a <agent>`
- `-m <model>`
- `-k 5`（正式 K5）
- `-k 1`（先做探针）
- `-n 1`
- `--env <h100_env>`
- `--upload`
- `--public` / `--private`

示例骨架：

```powershell
harbor run `
  -d terminal-bench/terminal-bench@3.0.0 `
  -i <task_name> `
  -a <agent> -m <model> `
  -k 1 `
  -n 1 `
  --env <h100_env> `
  --upload --private
```

正式 K5 时把 `-k 1` 改成 `-k 5`。

### 关于 `--env`

Harbor help 里支持多种环境类型，包含 `modal`、`daytona`、`docker` 等。真正要租 H100 时，选**实际能分配 H100 的那个环境**。

如果本地 Docker 路径没有 GPU 分配能力，就不要把 H100 任务硬塞进本地 docker-only 路径。

## 上传 / 提交流程

### 1) 本地正式 K5 先完成

先拿到本地全绿 job。

### 2) 上传到 Harbor Hub

用：

```text
harbor upload <job_dir> --public
```

如果只想备份、不想公开，就用：

```text
harbor upload <job_dir> --private
```

### 3) 重新上传时

- 不带 `--public/--private`：保持服务器端原可见性不变；
- 带 `--public`：改成公开；
- 带 `--private`：改成私有。

### 4) 记录 Hub URL

把返回的 Harbor Hub job URL 写回：

- `D:\terminal_bench_3_slai\runtime\tb3_k5_candidate_manifest.json`

这样后面能直接按 manifest 查证据，不用重新翻旧日志。

### 5) 如果还要走 leaderboard / 官方收录

注意：

- **Harbor Hub job 上传** ≠ **leaderboard 最终收录**
- Hub URL 只是作业证据和备份
- 最终是否进入公开榜单，要看当期 Harbor / Terminal-Bench 的官方提交入口和政策

不要把“已经上传 Hub”误当“已经上榜”。

## 失败怎么处理

### 本地没 H100 / GPU

直接判为硬件阻塞，归档，不要继续烧。

### 网络、镜像、apt、pip、build 失败

先补：

- 镜像预热
- 依赖缓存
- 代理/网络恢复
- 再开新的正式 K5

不要把 infra error 拼成成功批次。

### 部分 trial 成功

不算候选。整批失败就整批归档，不能剪裁拼接。

## 相关本地规则

配套说明见：

- `D:\terminal_bench_3_slai\reports\TB3_K5_EXECUTION_POLICY.md`
- `D:\terminal_bench_3_slai\reports\TB3_K5_OPS_CAPABILITY.md`

本文件只管“租 H100 + 提交/上传”这条最短路径。