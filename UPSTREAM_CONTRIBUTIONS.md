# Upstream Contributions

This index records publicly merged upstream Pull Requests authored by `huong8373tt-beep` and separates them from benchmark submission packages and work that remains under review or has another upstream state.

The account owner directs and authorizes contributions. Slai Agent Runtime assists with investigation, implementation, testing, review follow-up, and evidence organization.

## Merged engineering contributions

| Project | PR | Title / scope |
| --- | --- | --- |
| Microsoft PyRIT | [#3277](https://github.com/microsoft/PyRIT/pull/3277) | Add atomic attack context to scenario errors. |
| Microsoft PyRIT | [#3281](https://github.com/microsoft/PyRIT/pull/3281) | Add service shutdown error context. |
| Microsoft PyRIT | [#3333](https://github.com/microsoft/PyRIT/pull/3333) | Add runtime shutdown phase context. |
| Microsoft PyRIT | [#3351](https://github.com/microsoft/PyRIT/pull/3351) | Add Copilot cleanup phase context. |
| Microsoft PyRIT | [#3383](https://github.com/microsoft/PyRIT/pull/3383) | Type attack-technique seed factories with `Self`. |
| Microsoft PyRIT | [#3411](https://github.com/microsoft/PyRIT/pull/3411) | Type the adversarial-placeholder factory with `Self`. |
| Microsoft PyRIT | [#3441](https://github.com/microsoft/PyRIT/pull/3441) | Make attack-outcome logging exhaustive and surface unrecognized persisted values in regression coverage. |
| Microsoft SWE-bench-Live | [#54](https://github.com/microsoft/SWE-bench-Live/pull/54) | Fix pytest `XFAIL` handling in the evaluator. |
| Microsoft WinGet CLI | [#6582](https://github.com/microsoft/winget-cli/pull/6582) | Fix export output paths containing Unicode characters. |
| Tencent TeamAI CLI | [#1264](https://github.com/Tencent/teamai-cli/pull/1264) | Isolate the hook-reconcile test fixture from the contributor checkout. |
| Tencent TeamAI CLI | [#1291](https://github.com/Tencent/teamai-cli/pull/1291) | Retry report pushes when a prior attempt already committed the report locally. |
| Tencent BrowserSkill | [#473](https://github.com/Tencent/BrowserSkill/pull/473) | Clarify windowless Windows GUI-host startup for a foreground daemon. |
| Google Stellar Engine | [#338](https://github.com/google/stellar-engine/pull/338) | Apply configured Workbench notebook owners. |
| Google Stellar Engine | [#339](https://github.com/google/stellar-engine/pull/339) | Configure GitLab Cloud SQL private-network wiring. |
| Google Stellar Engine | [#340](https://github.com/google/stellar-engine/pull/340) | Omit VPC Service Controls log-sink ingress when logging is disabled. |
| Flash Linear Attention | [#1353](https://github.com/fla-org/flash-linear-attention/pull/1353) | Preserve `softplus` names in compiled Triton kernels. |

## Merged benchmark submission packages

These are public benchmark-result packages, not upstream product-code fixes:

| Project | PR | Scope |
| --- | --- | --- |
| SWE-bench-Live submission | [#28](https://github.com/SWE-bench-Live/submission/pull/28) | Python Lite smoke result. |
| SWE-bench-Live submission | [#29](https://github.com/SWE-bench-Live/submission/pull/29) | Python Lite success-only package. |
| SWE-bench-Live submission | [#30](https://github.com/SWE-bench-Live/submission/pull/30) | Windows 61 pass@1 verified-success snapshot. |
| SWE-bench-Live submission | [#31](https://github.com/SWE-bench-Live/submission/pull/31) | Python Lite 36/36 update after the XFAIL correction. |

## Windows evaluation contribution campaign

While participating in Windows-based SWE-bench-Live evaluation, Slai opened and advanced more than 60 focused Pull Requests across Microsoft/RepoLaunch and SWE-bench-Live evaluation repositories. The campaign includes work on Windows filesystem and path behavior, PowerShell and shell behavior, container preparation, task execution, evaluator semantics, and result archiving.

The approximate public campaign breakdown is:

| Area | Opened / advanced PRs | Status interpretation |
| --- | ---: | --- |
| [Microsoft/RepoLaunch](https://github.com/microsoft/RepoLaunch) | 21 | Individual PR pages are authoritative. |
| SWE-bench-Live evaluation repositories | 42 | Individual PR pages are authoritative. |

This campaign count is not a merged-count claim. It is included to describe the scope of sustained Windows evaluation work. The merged evaluator correctness contribution from this effort is [microsoft/SWE-bench-Live#54](https://github.com/microsoft/SWE-bench-Live/pull/54).

## Status boundary

Only Pull Requests visibly merged in their upstream repositories are placed in the two merged tables above. Open, closed, draft, or pending-review contributions are not counted there. Benchmark package merges and upstream product/evaluator fixes are also kept as separate categories.