# Slai Agent Runtime

Slai Agent Runtime is a private, cross-platform runtime for engineering work that may span multiple devices, test runs, or review cycles.

It can be used in two ways:

- a **local runtime** for personal computers and authorized devices; and
- a **cloud control plane** that stays online and coordinates the authorized nodes of an account.

Slai can work across Windows, Linux, macOS, and Android. A task can start on one device, use another authorized node for platform-specific work, and return its logs, artifacts, and follow-up work to the same account.

Slai is not tied to one model provider. Deployments can use mainstream standard-compatible model APIs while task execution, tools, device coordination, and result checking remain in the runtime.

This repository collects public records of Slai's upstream contributions, benchmark runs, and engineering work. It does not include the core runtime source, API keys, account tokens, private prompts, browser profiles, dependency caches, VM images, or full runtime dumps.

## Local runtime and cloud control plane

### Local runtime

Slai can run on, or connect to:

```text
Windows · Linux · macOS · Android
```

Local deployments support day-to-day interaction, source investigation, file and browser work, desktop or device operations, builds, tests, evaluations, and open-source collaboration.

### Cloud control plane

A server deployment can remain online as a control plane. It keeps sessions, tasks, registered nodes, and returned results separated by account scope, and routes work to the appropriate authorized node.

For example, a task can start on Windows, use an authorized Linux node for a Docker evaluation, CGO build, large test suite, artifact transfer, or server-maintenance task, then be inspected or continued from Windows, macOS, or Android.

This lets long-running work continue without depending entirely on one foreground device. Connected nodes expose only authorized capabilities; final operating-system permissions still depend on each node's deployment and access configuration.

## Engineering work that takes time

Some work takes more than one answer, device session, test run, or review cycle. Typical examples include:

```text
Repository investigation and bounded fixes
Repeated builds, tests, and debugging
Waiting for CI, bot, or maintainer feedback
Remote execution and artifact verification
Benchmark runs
Follow-up commits and maintenance
```

With account-owner direction and authorization, Slai can carry this work through investigation, implementation, validation, Pull Request submission, review follow-up, and record keeping. A queued task, a running job, and a verified result are not treated as the same thing.

## Public upstream contributions

Public GitHub records currently show **14 merged Pull Requests** authored by this account:

| Category | Count |
| --- | ---: |
| Upstream code, test, and evaluator contributions | 10 |
| SWE-bench-Live submission packages | 4 |

The merged engineering contributions cover error handling, type safety, evaluator correctness, Windows-compatible paths, test isolation, and compiled-kernel correctness. Links and scope notes are in [UPSTREAM_CONTRIBUTIONS.md](UPSTREAM_CONTRIBUTIONS.md).

### Selected merged contributions

| Project | Merged contribution | Scope |
| --- | --- | --- |
| Microsoft PyRIT | [#3277](https://github.com/microsoft/PyRIT/pull/3277), [#3281](https://github.com/microsoft/PyRIT/pull/3281), [#3333](https://github.com/microsoft/PyRIT/pull/3333), [#3351](https://github.com/microsoft/PyRIT/pull/3351) | Adds lifecycle context to scenario, service, runtime, and resource-cleanup errors. |
| Microsoft PyRIT | [#3383](https://github.com/microsoft/PyRIT/pull/3383), [#3411](https://github.com/microsoft/PyRIT/pull/3411) | Improves `Self` typing and subclass regression coverage for factories. |
| Microsoft SWE-bench-Live | [#54](https://github.com/microsoft/SWE-bench-Live/pull/54) | Corrects evaluator handling of pytest `XFAIL` outcomes. |
| Microsoft WinGet CLI | [#6582](https://github.com/microsoft/winget-cli/pull/6582) | Fixes export output paths containing Unicode / emoji characters. |
| Tencent TeamAI CLI | [#1264](https://github.com/Tencent/teamai-cli/pull/1264) | Prevents hook-reconcile tests from modifying a contributor's real Git checkout. |
| Flash Linear Attention | [#1353](https://github.com/fla-org/flash-linear-attention/pull/1353) | Preserves `softplus` and `softplus2` names in compiled Triton kernels. |

## Windows SWE-bench-Live work

While running SWE-bench-Live work on Windows, this account submitted **more than 60 focused Pull Requests** to [Microsoft/RepoLaunch](https://github.com/microsoft/RepoLaunch) and the [SWE-bench-Live](https://github.com/SWE-bench-Live) evaluation ecosystem.

They cover Windows paths and filesystem behavior, PowerShell and shell differences, container and environment preparation, task execution, result archiving, and pytest/evaluator semantics. This is a submitted-PR count, not a claim that every PR was merged. The merged evaluator correctness fix is [microsoft/SWE-bench-Live#54](https://github.com/microsoft/SWE-bench-Live/pull/54).

## Public benchmark and run records

- **[Harbor Hub public job records](https://hub.harborframework.com/users/huong8373tt-beep/jobs):** 155 published jobs, including Terminal-Bench 2.1 and later Terminal-Bench task runs.
- **[Terminal-Bench 2.1 #217](https://github.com/harbor-framework/terminal-bench-2-1/pull/217):** a public submission for GPT-5.5 xhigh + Slai Agent Runtime. Its materials cover 89 tasks × at least 5 trials (445 trials), report zero infrastructure errors, and passed 10/10 automated static checks. The PR received an approval and was later closed; the public timeline does not show a `/judge` result.
- **SWE-bench-Live:** merged public submission packages and the upstream evaluator correction are indexed in [BENCHMARKS.md](BENCHMARKS.md).

The Terminal-Bench #217 record is kept as a public submission and execution trail. It is not presented as an official leaderboard placement; official leaderboard inclusion is decided by the benchmark maintainers.

## Notes

This archive distinguishes merged work, work under review, closed work, independently run benchmarks, and official leaderboard results. Public project pages remain authoritative for upstream status and leaderboard inclusion.

External actions and public contributions are made with account-owner direction, review, and authorization.