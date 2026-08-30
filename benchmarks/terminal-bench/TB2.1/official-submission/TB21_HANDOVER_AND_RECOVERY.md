# TB21 Slai Submission — Handover / Recovery Note

Updated: 2026-08-22

## 1. Current outcome

Terminal-Bench 2.1 official dataset run has been completed and publicly uploaded through Harbor.

Final local/public audit:

```text
accepted_task_count = 89
accepted_trial_count = 445
public_link_count = 89
validated_clean_5_of_5_count = 89
visibility_summary = {"public": 89}
problems = []
```

Primary audit file:

```text
D:\terminal_bench_slai\runtime\tb21_final_public_audit_20260822_134053.json
```

89 public Harbor job links:

```text
D:\terminal_bench_slai\runtime\tb21_final_public_submission_links_20260822_134053.txt
```

Submission package:

```text
D:\terminal_bench_slai\runtime\tb21_submission_package_20260822_134053.zip
```

## 2. Public visibility cleanup

Harbor account cleanup was performed after final public upload.

Result:

```text
Formal TB21 clean jobs kept public: 89 / 89
Non-final / TB3 / failed / polluted / smoke jobs set private: 62 / 62
```

Verification file:

```text
D:\terminal_bench_slai\runtime\harbor_direct_visibility_verify_20260822_150028.json
```

## 3. GitHub PR

PR:

```text
https://github.com/harbor-framework/terminal-bench-2-1/pull/216
```

Issue:

```text
https://github.com/harbor-framework/terminal-bench-2-1/issues/215
```

Submission JSON in PR:

```text
leaderboard/submissions/2026-08-22-openai-gpt-5-5-xhigh-none-slai-tb-v3-passive-supervisor.json
```

Local copy:

```text
D:\terminal_bench_slai\terminal-bench-2-1-main\leaderboard\submissions\2026-08-22-openai-gpt-5-5-xhigh-none-slai-tb-v3-passive-supervisor.json
```

PR branch:

```text
huong8373tt-beep/terminal-bench-2-1:submission/2026-08-22-openai-gpt-5-5-xhigh-slai
```

Important note: the first PR static-analysis run failed because official CI matches `source_filter.agent` against `job.config.agents[].name`. Our uploaded job configs originally had the Python import path:

```text
slai_tb_agent.agent_v3:SlaiTBPassiveAgent
```

while the Harbor trial/eval agent identity and submission filter use:

```text
slai-tb-v3-passive-supervisor
```

The 89 Harbor public job configs were repaired server-side to use the display/CI agent key in `config.agents[].name`, without changing trials, rewards, task refs, trajectories, or local job evidence.

Repair verification:

```text
D:\terminal_bench_slai\runtime\tb21_harbor_job_config_agent_name_repair_20260822_154449.json
```

A same-tree empty commit was pushed to retrigger PR CI:

```text
old PR head: bb55d27f88def8b66ae968aae2b6b0bd66bcb3bd
new PR head: 091db16cd6446ee564d0e712b5a625795669b6c9
trigger record: D:\terminal_bench_slai\runtime\tb21_pr_empty_commit_trigger_20260822_155037.json
```

As of the last manual check in this handover, the new static-analysis run had started and was still in progress, not yet final.

## 4. Public statement / positioning

Short public statement:

```text
D:\terminal_bench_slai\TB21_SUBMISSION_STATEMENT.md
```

Core wording:

- Slai Agent Runtime is a proprietary closed-source agent runtime.
- The uploaded Harbor jobs show the model/API configuration.
- Runtime-side model configuration was fixed as GPT-5.5 xhigh throughout the run.
- This is a system-level agent-runtime result, not a claim that Slai is a foundation model.
- Local evaluation environment and execution harness were set up/adapted by Slai on a personal machine and home network.
- Human involvement was limited to high-level supervision/scheduling/publication decisions, not per-task solving.

## 5. If continuing later

Recommended checks:

```powershell
gh pr view 216 --repo harbor-framework/terminal-bench-2-1 --json headRefOid,statusCheckRollup,state,mergeable,reviewDecision,comments,url,updatedAt
```

If PR CI passes, record the status in this file and no further action is needed unless maintainers ask questions.

If CI fails again:

1. Read the GitHub Actions static-analysis sticky comment.
2. Do not change rewards/trials/task refs.
3. Fix only metadata/config mismatch if the failure is about submission plumbing.
4. Leave a clear note in PR if needed.

## 6. Local important files

Core files to keep:

```text
D:\terminal_bench_slai\TB21_HANDOVER_AND_RECOVERY.md
D:\terminal_bench_slai\TB21_SUBMISSION_STATEMENT.md
D:\terminal_bench_slai\runtime\tb21_official_k5_submit_manifest.json
D:\terminal_bench_slai\runtime\tb21_final_public_audit_20260822_134053.json
D:\terminal_bench_slai\runtime\tb21_final_public_submission_links_20260822_134053.txt
D:\terminal_bench_slai\runtime\tb21_final_public_result_summary_20260822_134053.csv
D:\terminal_bench_slai\runtime\tb21_submission_package_20260822_134053.zip
D:\terminal_bench_slai\runtime\tb21_harbor_job_config_agent_name_repair_20260822_154449.json
D:\terminal_bench_slai\runtime\harbor_direct_visibility_verify_20260822_150028.json
D:\terminal_bench_slai\runtime\tb21_pr_empty_commit_trigger_20260822_155037.json
D:\terminal_bench_slai\terminal-bench-2-1-main\leaderboard\submissions\2026-08-22-openai-gpt-5-5-xhigh-none-slai-tb-v3-passive-supervisor.json
```

## 7. Backup policy

A lightweight recovery backup is recommended on E: drive rather than copying the entire 20GB+ working tree.

Reason:

- D: keeps full working state.
- Harbor holds public job artifacts.
- E: backup should preserve final evidence, PR materials, scripts, manifest, and accepted job result directories.
- Huge dependency caches and scratch runtime are not necessary for submission recovery and can be rebuilt if needed.