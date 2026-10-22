# Slai Agent Runtime

Slai Agent Runtime is a private, cross-platform runtime for engineering work that may span multiple devices, test runs, or review cycles.

It runs locally and can, with the owner's authorization, continue work across connected devices or services.

Slai works across Windows, Linux, macOS, and Android. The same project can move between authorized devices while keeping its results and follow-up work together.

Slai is not tied to one model provider. Deployments can use mainstream standard-compatible model APIs while task execution, tools, device coordination, and result checking remain in the runtime.

This repository collects public records of Slai's upstream contributions, benchmark runs, and engineering work. It does not include the core runtime source, API keys, account tokens, private prompts, browser profiles, dependency caches, VM images, or full runtime dumps.

## Why this exists

Slai's developer does not have a programming background and does not need to write code directly to take part in software engineering.

The developer usually expresses a direction, goal, or problem in short, natural language. Slai then investigates the situation, reads code and documentation, identifies the relevant constraints and risks, and works toward a checkable outcome:

```text
Goal or problem
→ investigation and judgment
→ implementation and testing
→ result verification
→ public contribution, record keeping, or follow-up work
```

The developer's role is to provide direction, goal descriptions, and feedback from using Slai. That feedback also helps Slai find, maintain, and improve its own runtime framework.

This is an ongoing experiment in human–AI collaboration: lowering the knowledge barrier that keeps many people from participating in real software engineering, while using AI to carry ideas through to implementations, tests, contributions, and results.

## Model training and capability research

At today's personal-compute budget, Slai Agent Runtime relies primarily on cloud-model APIs for its engineering work. [Slai Model Lab](https://github.com/huong8373tt-beep/slai.life-model-lab-docs) is a separate private training, model-runtime, and experimentation system for the longer-term path: as personal compute, hardware efficiency, and accessible models improve, individuals should be able to train, operate, and evaluate more of their own models.

The two systems are complementary. Runtime work can produce and organize structured task experience; Model Lab studies how selected private experience can be reviewed, used for training, evaluated, and—when it passes regression checks—made available to later Runtime work. Its recorded experiments span text, speech, image, video, multimodal, and homegrown models.

This is an effort to build the training, recovery, and evaluation foundation ahead of that future. The Runtime does not depend on self-trained models, and not every interaction is automatically used for training.

## Local runtime

```text
Windows · Linux · macOS · Android
```

Local deployments support conversation, research, file and browser work, authorized device operations, builds, tests, and open-source collaboration.

Slai supports foreground/background agent collaboration and can use authorized devices or servers for platform-specific work. A project can remain connected across tool runs, test failures, CI waits, reviews, and recoverable restarts—over hours or days, and across longer maintenance cycles.

In observed continuous, non-cold-start work, stable requests and provider prompt-cache reuse can yield roughly **95–99%** input-token cache hits. This is an efficiency observation, not an accuracy claim.

## Public upstream contributions

Public GitHub records currently show **20 merged Pull Requests** authored by this account:

| Category | Count |
| --- | ---: |
| Upstream engineering contributions | 16 |
| SWE-bench-Live submission packages | 4 |

The engineering work covers reliability, type safety, evaluator correctness, Windows compatibility, testing, cloud configuration, and compiled-kernel correctness. Links and scope notes are in [UPSTREAM_CONTRIBUTIONS.md](UPSTREAM_CONTRIBUTIONS.md).

### Selected merged contributions

| Project | Merged contribution | Scope |
| --- | --- | --- |
| Microsoft PyRIT | [#3277](https://github.com/microsoft/PyRIT/pull/3277), [#3281](https://github.com/microsoft/PyRIT/pull/3281), [#3333](https://github.com/microsoft/PyRIT/pull/3333), [#3351](https://github.com/microsoft/PyRIT/pull/3351) | Adds lifecycle context to scenario, service, runtime, and resource-cleanup errors. |
| Microsoft PyRIT | [#3383](https://github.com/microsoft/PyRIT/pull/3383), [#3411](https://github.com/microsoft/PyRIT/pull/3411) | Improves `Self` typing and subclass regression coverage for factories. |
| Microsoft PyRIT | [#3441](https://github.com/microsoft/PyRIT/pull/3441) | Makes attack-outcome logging exhaustive and surfaces unrecognized persisted values in regression coverage. |
| Microsoft SWE-bench-Live | [#54](https://github.com/microsoft/SWE-bench-Live/pull/54) | Corrects evaluator handling of pytest `XFAIL` outcomes. |
| Microsoft WinGet CLI | [#6582](https://github.com/microsoft/winget-cli/pull/6582) | Fixes export output paths containing Unicode / emoji characters. |
| Tencent TeamAI CLI | [#1264](https://github.com/Tencent/teamai-cli/pull/1264), [#1291](https://github.com/Tencent/teamai-cli/pull/1291) | Isolates hook-reconcile tests from contributor checkouts and makes report-push retries recover an earlier local commit. |
| Tencent BrowserSkill | [#473](https://github.com/Tencent/BrowserSkill/pull/473) | Documents the correct windowless Windows GUI-host startup boundary for a foreground daemon. |
| Google Stellar Engine | [#338](https://github.com/google/stellar-engine/pull/338), [#339](https://github.com/google/stellar-engine/pull/339), [#340](https://github.com/google/stellar-engine/pull/340) | Fixes Workbench notebook owners, GitLab Cloud SQL private-network wiring, and conditional VPC Service Controls log-sink ingress. |
| Flash Linear Attention | [#1353](https://github.com/fla-org/flash-linear-attention/pull/1353) | Preserves `softplus` and `softplus2` names in compiled Triton kernels. |

## Windows SWE-bench-Live work

While running SWE-bench-Live work on Windows, this account submitted **more than 60 focused Pull Requests** to [Microsoft/RepoLaunch](https://github.com/microsoft/RepoLaunch) and the [SWE-bench-Live](https://github.com/SWE-bench-Live) evaluation ecosystem.

They cover Windows paths and filesystem behavior, PowerShell and shell differences, container and environment preparation, task execution, result archiving, and pytest/evaluator semantics. This is a submitted-PR count, not a claim that every PR was merged. The merged evaluator correctness fix is [microsoft/SWE-bench-Live#54](https://github.com/microsoft/SWE-bench-Live/pull/54).

## Public benchmark and run records

- **[Harbor Hub public job records](https://hub.harborframework.com/users/huong8373tt-beep/jobs):** 155 published jobs, including Terminal-Bench 2.1 and later Terminal-Bench task runs. The later-task archive includes complete K=5 results for **63 of 66 tasks**; each published covered task is a **5/5 successful run (100% within the documented 63-task coverage)**. The remaining three tasks were not run because the required hardware was not available.
- **[Terminal-Bench 2.1 #217](https://github.com/harbor-framework/terminal-bench-2-1/pull/217):** a public submission for GPT-5.5 xhigh + Slai Agent Runtime. Its submitted archive reports **100.00% accuracy** across 89 tasks × at least 5 trials: **445/445 successful trials**, zero reported infrastructure errors, and 10/10 automated static checks passed. The PR received an approval and was later closed; the public timeline does not show a `/judge` result.
- **SWE-bench-Live:** merged public submission packages and the upstream evaluator correction are indexed in [BENCHMARKS.md](BENCHMARKS.md).

The Terminal-Bench #217 record is kept as a public submission and execution trail. It is not presented as an official leaderboard placement; official leaderboard inclusion is decided by the benchmark maintainers.

## Notes

This archive distinguishes merged work, work under review, closed work, independently run benchmarks, and official leaderboard results. Public project pages remain authoritative for upstream status and leaderboard inclusion.

This repository does not claim that autonomous software engineering is solved. It records an evolving collaboration between a developer who does not write code directly and an Agent Runtime that investigates, implements, tests, follows up, and keeps records.

External actions and public contributions are made with the account owner's stated goals and authorization.