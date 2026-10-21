# Slai Agent Runtime — Public Evidence Archive

Slai Agent Runtime is a private, cross-platform runtime for real engineering work and long-horizon tasks.

It has two deployment forms that can work together:

- a **local-native runtime** for personal computers and controlled devices; and
- an **account-scoped cloud control plane** that stays online and coordinates authorized nodes.

The same account can connect authorized Windows, Linux, macOS, and Android nodes. A task can begin on one device, use another node for a platform-specific workload, and return its status, artifacts, and next actions to the same account workflow.

Slai is decoupled from any single model provider. Model calls are separate from task execution, tools, device coordination, and result verification, allowing deployments to use mainstream standard-compatible model APIs without rebuilding the workflow around one provider.

This repository is a public evidence archive for Slai capabilities, benchmark records, and upstream engineering contributions. It intentionally excludes core runtime source, API keys, account tokens, private prompts, browser profiles, dependency caches, VM images, and full runtime dumps.

## Local runtime and cloud control plane

### Local-native runtime

Slai can run on or connect to:

```text
Windows · Linux · macOS · Android
```

A local runtime is suited to day-to-day interaction, source investigation, file and browser work, desktop or device operations, builds, tests, evaluations, and open-source collaboration.

### Account-scoped cloud control plane

A server deployment can remain online as an account-scoped control plane. Within an authorized account scope, it routes sessions and tasks to appropriate registered nodes and returns logs, artifacts, and results to the originating workflow.

```text
Account
→ sessions and tasks
→ authorized cross-platform nodes
→ controlled execution and result collection
→ continue from any connected device
```

For example, a task can start on Windows, use an authorized Linux node for a Docker evaluation, CGO build, large test suite, artifact transfer, or server-maintenance work, and later be inspected or continued from Windows, macOS, or Android.

The cloud control plane keeps long-running work from depending entirely on one foreground device. Node capabilities remain explicitly authorized; final operating-system permissions depend on each node's deployment and access configuration.

## Long-horizon engineering work

Slai is designed for work that does not fit in a single answer or a single device session, including:

```text
Repository investigation and bounded fixes
Repeated builds, tests, and debugging
Waiting for CI, bot, or maintainer feedback
Remote execution and artifact verification
Long-running benchmark work
Follow-up commits and maintenance
```

Under developer direction and account-owner authorization, Slai can carry a workflow through investigation, implementation, validation, Pull Request submission, review follow-up, and evidence archiving. A started task, a delivered message, a running job, and a verified result are treated as different states.

## Public upstream contributions

Public GitHub records currently show **14 merged Pull Requests** authored by this account:

| Category | Count |
| --- | ---: |
| Upstream code, test, and evaluator contributions | 10 |
| SWE-bench-Live submission packages | 4 |

The merged engineering contributions cover error handling, type safety, evaluator correctness, Windows-compatible paths, test isolation, and compiled-kernel correctness. Detailed links and scope notes are in [UPSTREAM_CONTRIBUTIONS.md](UPSTREAM_CONTRIBUTIONS.md).

### Selected merged contributions

| Project | Merged contribution | Scope |
| --- | --- | --- |
| Microsoft PyRIT | [#3277](https://github.com/microsoft/PyRIT/pull/3277), [#3281](https://github.com/microsoft/PyRIT/pull/3281), [#3333](https://github.com/microsoft/PyRIT/pull/3333), [#3351](https://github.com/microsoft/PyRIT/pull/3351) | Adds lifecycle context to scenario, service, runtime, and resource-cleanup errors. |
| Microsoft PyRIT | [#3383](https://github.com/microsoft/PyRIT/pull/3383), [#3411](https://github.com/microsoft/PyRIT/pull/3411) | Improves `Self` typing and subclass regression coverage for factories. |
| Microsoft SWE-bench-Live | [#54](https://github.com/microsoft/SWE-bench-Live/pull/54) | Corrects evaluator handling of pytest `XFAIL` outcomes. |
| Microsoft WinGet CLI | [#6582](https://github.com/microsoft/winget-cli/pull/6582) | Fixes export output paths containing Unicode / emoji characters. |
| Tencent TeamAI CLI | [#1264](https://github.com/Tencent/teamai-cli/pull/1264) | Prevents hook-reconcile tests from modifying a contributor's real Git checkout. |
| Flash Linear Attention | [#1353](https://github.com/fla-org/flash-linear-attention/pull/1353) | Preserves `softplus` and `softplus2` names in compiled Triton kernels. |

## Windows SWE-bench-Live evaluation practice

During sustained Windows-based SWE-bench-Live evaluation, environment preparation, and result-verification work, Slai opened and advanced **more than 60 focused upstream Pull Requests** across [Microsoft/RepoLaunch](https://github.com/microsoft/RepoLaunch) and the [SWE-bench-Live](https://github.com/SWE-bench-Live) evaluation ecosystem.

The work addresses Windows path and filesystem differences, PowerShell and shell behavior, container and environment preparation, task execution, result archiving, and pytest/evaluator semantics. These are not represented as 60+ merged contributions: each PR retains its own public upstream status. The merged evaluator correctness fix is [microsoft/SWE-bench-Live#54](https://github.com/microsoft/SWE-bench-Live/pull/54).

## Public benchmark and run evidence

- **[Harbor Hub public job records](https://hub.harborframework.com/users/huong8373tt-beep/jobs):** 155 published jobs, including Terminal-Bench 2.1 and later Terminal-Bench task runs.
- **[Terminal-Bench 2.1 #217](https://github.com/harbor-framework/terminal-bench-2-1/pull/217):** a public submission record for GPT-5.5 xhigh + Slai Agent Runtime. Its submitted materials cover 89 tasks × at least 5 trials (445 trials), report zero infrastructure errors, and passed 10/10 automated static checks. The PR received a public approval and was later closed; its public timeline does not show a `/judge` result or a public technical finding that rejects the submitted materials.
- **SWE-bench-Live:** merged public submission packages and the upstream evaluator correction are indexed in [BENCHMARKS.md](BENCHMARKS.md).

The Terminal-Bench #217 record is preserved as a public submission, automated-check, review, and Harbor-evidence trail. It is **not** described as an official leaderboard placement. Official leaderboard display and inclusion remain decisions of the relevant benchmark maintainers.

## Reading this archive

This archive distinguishes merged work, work under review, closed work, independently operated benchmark runs, and official leaderboard results. Public source pages remain authoritative for upstream status, benchmark inclusion, and final maintainer conclusions.

## Account-owner role

The account owner sets direction, authorizes external actions, reviews consequential work, and remains responsible for the account and published material. Slai performs investigation, implementation, testing, cross-platform coordination, controlled execution, contribution follow-up, and evidence organization within that boundary.