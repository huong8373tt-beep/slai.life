# SWE-bench-Live Official Merged PR Evidence

Maintained and uploaded by **Slai** under developer direction.

This file is a lightweight public evidence index. The canonical evidence is the official merged GitHub PRs; this archive only records stable navigation and public metadata so future work does not have to reconstruct it from memory.

- Retrieved at: `2026-08-31T04:13:51+00:00`
- Source: GitHub Pulls API via `gh api`
- Scope: public merged PR metadata only; no local SWE runtime dump, VM cache, token, or answer trajectory is included.

## Merged PR table

| PR | Repository | Scope | Merged at | Merge commit | Public note |
| --- | --- | --- | --- | --- | --- |
| [SWE-bench-Live/submission#28](https://github.com/SWE-bench-Live/submission/pull/28) | `SWE-bench-Live/submission` | Python Lite smoke result | `2026-08-19T13:27:17Z` | `f316992bf993` | 1 submitted / 1 success / 0 failure / 0 error / 0 incomplete |
| [SWE-bench-Live/submission#29](https://github.com/SWE-bench-Live/submission/pull/29) | `SWE-bench-Live/submission` | Python Lite success-only package | `2026-08-25T06:39:09Z` | `79123646eb6e` | 23 official resolved instances |
| [SWE-bench-Live/submission#30](https://github.com/SWE-bench-Live/submission/pull/30) | `SWE-bench-Live/submission` | Windows 61 success snapshot | `2026-08-28T23:42:42Z` | `57d73024373a` | 8 official resolved Windows instances; partial snapshot, not a complete Windows 61 result |
| [SWE-bench-Live/submission#31](https://github.com/SWE-bench-Live/submission/pull/31) | `SWE-bench-Live/submission` | Python Lite package update after evaluator fix | `2026-08-30T12:02:55Z` | `28b634277bef` | 36/36 after upstream pytest XFAIL parser fix |
| [microsoft/SWE-bench-Live#54](https://github.com/microsoft/SWE-bench-Live/pull/54) | `microsoft/SWE-bench-Live` | Upstream evaluator correctness fix | `2026-08-29T00:00:39Z` | `7c5ee6c11595` | Fix pytest XFAIL handling in evaluator; Slai-Agent Runtime identified and submitted the correction |

## Why this is enough for the public archive

SWE-bench-Live differs from the Terminal-Bench raw job archive: the important SWE evidence is already merged upstream in public repositories. For that reason this public archive keeps compact PR-level evidence rather than uploading large local evaluator/runtime directories.

## Status wording

These PRs are preserved as merged Slai-Agent Runtime contributions, including partial/snapshot submissions and the upstream evaluator correctness fix. They should not be overstated as final complete leaderboard entries unless the official benchmark maintainers display them that way.
