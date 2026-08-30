# Terminal-Bench TB4-0 / Slai Agent Runtime Archive

Local source workspace: `D:\terminal_bench_3_slai`  
Local docs/dataset label observed: `terminal-bench/terminal-bench@3.0.0`  
Owner-facing archive label: `TB4-0`

## Local accepted set

- Accepted task count: 60
- Accepted trial count: 300
- K per accepted task: 5
- Reward mean for accepted tasks: all `1.0` = true
- Public Harbor job links with explicit public evidence recorded: 59
- Raw Hub URL count in manifest/source_jobs: 60

One manifest row (`live-database-cutover`) has a Hub URL but missing `hub_visibility` in the local accepted manifest, so the audit conservatively counts 59 public-evidence URLs; see `public_visibility_audit.json`.

## Files

- `accepted_k5_candidate_manifest.json`: full local accepted K5 candidate manifest.
- `public_harbor_job_links.txt`: public Harbor job URLs.
- `harbor_source_jobs_60.json`: leaderboard-like `source_jobs` JSON derived from the manifest. Metrics are intentionally left null because official leaderboard judging/inclusion is separate.
- `result_summary.csv`: task-level summary.
- `public_visibility_audit.json`: visibility-evidence summary.

## Status

This archive records independently reproducible Slai Agent Runtime benchmark evidence. It does not claim official leaderboard inclusion is complete.
