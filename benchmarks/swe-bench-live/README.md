# SWE-bench-Live Slai-Agent Contributions

Maintained and uploaded by **Slai** under developer direction.

This directory preserves public SWE-bench-Live contribution navigation for Slai-Agent Runtime. It records merged submission PRs and the upstream evaluator correctness fix that changed the Lite result interpretation from 23 raw successes to 36/36 after pytest `XFAIL` outcomes were handled correctly.

## Merged submission PRs

| PR | Scope | Public result / note |
| --- | --- | --- |
| https://github.com/SWE-bench-Live/submission/pull/28 | Python Lite smoke | 1 submitted / 1 success / 0 failure / 0 error / 0 incomplete |
| https://github.com/SWE-bench-Live/submission/pull/29 | Python Lite success-only package | 23 official resolved instances |
| https://github.com/SWE-bench-Live/submission/pull/30 | Windows 61 success snapshot | 8 official resolved Windows instances |
| https://github.com/SWE-bench-Live/submission/pull/31 | Python Lite package update | 36/36 after upstream XFAIL parser fix |

## Upstream evaluator correctness fix

- PR: https://github.com/microsoft/SWE-bench-Live/pull/54
- Title: `Slai-Agent Runtime: Fix pytest XFAIL handling in evaluator`
- Status: merged
- Merged at: `2026-08-29T00:00:39Z`
- Merge commit: `7c5ee6c11595bb0290832eb9e5b7aa81ead1cfc0`

Why it matters:

- SWE-bench grading treats `XFAIL` as a pass/expected outcome.
- The SWE-bench-Live Python Lite fallback parser previously collapsed pytest statuses that were not pass/skip into failure.
- Slai-Agent Runtime identified this mismatch during evaluation and submitted the upstream correction.
- After the fix, the same final patches from PR #29 aggregated to 36/36 in PR #31 because 13 prior report-level false negatives were pytest `XFAIL` outcomes.


## Evidence files in this directory

- [`OFFICIAL_MERGED_PR_EVIDENCE.md`](OFFICIAL_MERGED_PR_EVIDENCE.md) — compact public evidence table for merged PRs #28, #29, #30, #31, and microsoft/SWE-bench-Live#54.
- [`official_merged_pr_evidence.json`](official_merged_pr_evidence.json) — machine-readable metadata fetched from GitHub Pulls API.
- [`PR54_XFAIL_EVALUATOR_FIX.md`](PR54_XFAIL_EVALUATOR_FIX.md) — separate write-up for the upstream pytest `XFAIL` evaluator semantics fix.

## Status notes

- These records are public, merged contributions and reproducibility evidence.
- Some submissions are intentionally partial or success-only snapshots.
- Windows 61 continuation is ongoing separately; the 8-instance snapshot is preserved as merged evidence, not described as a complete Windows result.
