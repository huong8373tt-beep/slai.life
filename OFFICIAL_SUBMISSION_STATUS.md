# Official Submission Status

This file records external submission / contribution status for the public Slai archive. It is written as evidence navigation, not as a private runtime dump.

## Terminal-Bench 2.1

- Original user PR: https://github.com/harbor-framework/terminal-bench-2-1/pull/216
- Promoted leaderboard-owned PR: https://github.com/harbor-framework/terminal-bench-2-1/pull/217
- Local archive package: `benchmarks/terminal-bench/TB2.1/official-submission/`
- Static archive analysis recorded 445 trials, no errors, 100.00% accuracy for the preserved TB2.1 package.

## Terminal-Bench / TB4 public archive

- Public Harbor jobs: https://hub.harborframework.com/users/huong8373tt-beep/jobs
- Public-facing coverage label: **TB4 63/66 K5 tasks**.
- Repository archive path: `benchmarks/terminal-bench/TB4-0/`
- The repository preserves a sanitized evidence package plus public Harbor links. Official leaderboard inclusion/status is not treated as completed by this archive.
- Continuation is temporarily paused due to H100 hardware constraints and unclear official acceptance policy for third-party/proxy testing.

## SWE-bench-Live submissions

Merged submission PRs:

- #28 — Python Lite smoke result, 1 submitted / 1 success: https://github.com/SWE-bench-Live/submission/pull/28
- #29 — Python Lite success-only package, 23 official resolved instances: https://github.com/SWE-bench-Live/submission/pull/29
- #30 — Windows 61 pass@1 verified success snapshot, 8 official resolved instances: https://github.com/SWE-bench-Live/submission/pull/30
- #31 — Python Lite package update to 36/36 after XFAIL evaluator fix: https://github.com/SWE-bench-Live/submission/pull/31

These are merged partial/snapshot contributions. They should not be described as a final complete SWE-bench-Live leaderboard submission.

## SWE-bench-Live upstream evaluator fix

- #54 — Slai-Agent Runtime: Fix pytest XFAIL handling in evaluator: https://github.com/microsoft/SWE-bench-Live/pull/54
- Status: merged upstream on 2026-08-29T00:00:39Z
- Merge commit: `7c5ee6c11595bb0290832eb9e5b7aa81ead1cfc0`

This contribution corrected evaluator semantics: pytest `XFAIL` means an expected failure remained expected and should be treated consistently with SWE-bench grading semantics, not collapsed into a failure.

## Neutral public wording

These are Slai-Agent Runtime benchmark result artifacts and merged contribution records. Official leaderboard display or inclusion is a separate process controlled by benchmark maintainers.
