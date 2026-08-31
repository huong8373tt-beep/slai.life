# Terminal-Bench TB4-0 / Slai Agent Runtime Archive

Maintained and uploaded by **Slai** under developer direction.

Local source workspace: `D:\terminal_bench_3_slai`  
Local docs/dataset label observed: `terminal-bench/terminal-bench@3.0.0`  
Owner-facing archive label: `TB4-0`

## Headline

- **TB4 coverage preserved here:** **63/66 K5 tasks**
- **Primary live evidence:** https://hub.harborframework.com/users/huong8373tt-beep/jobs
- Further TB4 continuation is temporarily paused because of H100 hardware constraints and unresolved official guidance on whether third-party/proxy execution should be accepted.

## How to read the numbers

The headline for this archive is **63/66 K5 tasks**.

Some files in this directory mention **60**, **300**, or **59/60**. Those numbers come from an older, sanitized local snapshot and should not be read as the TB4 headline:

- **60 tasks** = tasks present in the local manifest snapshot copied from `D:\terminal_bench_3_slai`.
- **300 trials** = 60 local-snapshot tasks × K=5.
- **59/60 public visibility** = a conservative link-visibility check inside that older 60-row snapshot.

That old snapshot is retained for auditability because it is part of the evidence trail. It is not the full public coverage count. The public-facing TB4 statement for this archive is **63/66 K5 tasks**, with the live Harbor jobs page as the primary navigation point.

## Files

- `accepted_k5_candidate_manifest.json`: older 60-task local accepted K5 candidate manifest snapshot.
- `public_harbor_job_links.txt`: public Harbor job URLs from the older local snapshot.
- `harbor_source_jobs_60.json`: leaderboard-like `source_jobs` JSON derived from the older 60-row local snapshot. Metrics are intentionally left null because official leaderboard judging/inclusion is separate.
- `result_summary.csv`: task-level summary for the older local snapshot.
- `public_visibility_audit.json`: scope-aware visibility audit clarifying that 59/60 is only the older local snapshot audit.
- `tb4_public_coverage_audit.json`: public-facing TB4 63/66 coverage note and live Hub navigation.

## Status

This archive records independently reproducible Slai Agent Runtime benchmark evidence. It does not claim official leaderboard inclusion is complete.
