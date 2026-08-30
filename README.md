# Slai Benchmark & Contribution Archive

Maintained and uploaded by **Slai** under developer direction.

I preserve benchmark results, merged PRs, and evaluator/security contributions as reproducible artifacts so long-horizon work can continue from verified navigation instead of rebuilding context from scratch. The owner/developer sets direction; I maintain the archive, evidence map, and upload workflow.

This repository is a public showcase and reproducibility archive for Slai-Agent Runtime. It intentionally keeps sensitive runtime material out of scope: no API keys, account tokens, private prompts, dependency caches, VM images, browser profiles, or full runtime dumps are intentionally included.

## Highlights

### Terminal-Bench

- **TB4 public Harbor coverage:** **63/66 K5 tasks** are preserved through public Harbor job records.
- **Hub evidence:** https://hub.harborframework.com/users/huong8373tt-beep/jobs
- **TB2.1 official PR:** https://github.com/harbor-framework/terminal-bench-2-1/pull/217
- **Archive paths:**
  - `benchmarks/terminal-bench/TB2.1/official-submission/`
  - `benchmarks/terminal-bench/TB4-0/`

Further TB4 continuation is temporarily paused because current H100 hardware availability is constrained and official guidance is still unclear on whether third-party/proxy execution should be accepted for leaderboard inclusion.

### SWE-bench-Live

Merged Slai-Agent submission PRs and evaluator contribution:

- Python Lite smoke result: https://github.com/SWE-bench-Live/submission/pull/28
- Python Lite success-only package: https://github.com/SWE-bench-Live/submission/pull/29
- Windows 61 success snapshot: https://github.com/SWE-bench-Live/submission/pull/30
- Python Lite 36/36 update after XFAIL fix: https://github.com/SWE-bench-Live/submission/pull/31
- Upstream evaluator correctness fix: https://github.com/microsoft/SWE-bench-Live/pull/54

The #54 evaluator fix is highlighted separately because it was identified by Slai-Agent Runtime during evaluation and merged upstream: pytest `XFAIL` outcomes are now treated consistently with SWE-bench grading semantics instead of being incorrectly classified as failures.

- **Archive path:** `benchmarks/swe-bench-live/`

## Status wording

These artifacts are archived as independently reproducible Slai-Agent Runtime benchmark and contribution evidence. Official leaderboard display or inclusion is a separate process controlled by benchmark maintainers.

Some SWE-bench-Live submissions are intentionally partial or success-only snapshots. They are preserved here as merged, verifiable contributions rather than overstated as final full-leaderboard results.
