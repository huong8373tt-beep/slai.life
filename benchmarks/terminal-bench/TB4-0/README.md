# Terminal-Bench TB4-0 / Slai Agent Runtime Archive

Maintained and uploaded by **Slai** under developer direction.

Local source workspace: `D:\terminal_bench_3_slai`  
Local docs/dataset label observed: `terminal-bench/terminal-bench@3.0.0`  
Owner-facing archive label: `TB4-0`

## Public coverage headline

- **TB4 public-facing coverage:** **63/66 K5 tasks**
- **Primary live evidence:** https://hub.harborframework.com/users/huong8373tt-beep/jobs
- Harbor Hub is paginated and contains more than sixty public Slai K5 job uploads. The 60-row files in this directory are a sanitized local manifest snapshot, not the full public coverage count.
- Further TB4 continuation is temporarily paused due to H100 hardware constraints and unresolved official guidance on whether third-party/proxy execution should be accepted.

## Local manifest snapshot

These files preserve a conservative local extract from `D:\terminal_bench_3_slai`:

- Local accepted manifest task count: 60
- Local accepted trial count: 300
- K per accepted task: 5
- Reward mean for local accepted manifest tasks: all `1.0` = true
- Raw Hub URL count in the local manifest/source_jobs snapshot: 60
- Conservative public-visibility count inside that one snapshot: 59

The old 59/60 audit is intentionally retained as a narrow manifest-snapshot audit. It must not be used as the TB4 headline. The public-facing TB4 headline for this archive is **63/66 K5 tasks**.

## Files

- `accepted_k5_candidate_manifest.json`: 60-task local accepted K5 candidate manifest snapshot.
- `public_harbor_job_links.txt`: public Harbor job URLs from the local snapshot.
- `harbor_source_jobs_60.json`: leaderboard-like `source_jobs` JSON derived from the 60-row local snapshot. Metrics are intentionally left null because official leaderboard judging/inclusion is separate.
- `result_summary.csv`: task-level summary for the local snapshot.
- `public_visibility_audit.json`: scope-aware visibility audit clarifying that 59/60 is only the local snapshot audit.
- `tb4_public_coverage_audit.json`: public-facing TB4 63/66 coverage note and live Hub navigation.

## Status

This archive records independently reproducible Slai Agent Runtime benchmark evidence. It does not claim official leaderboard inclusion is complete.
