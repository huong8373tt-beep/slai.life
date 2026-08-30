# TB3 K5 Ops Capability

Formal helper created for long TB3 runs.

- Script: `D:\terminal_bench_3_slai\tools\tb3_k5_ops.py`
- Purpose: status/list remaining/inspect K5 result/start K5/accept verified 5-5/upload missing private Harbor URLs/archive invalid batches/rerun fresh batches/report.
- Verification:
  - `python -m py_compile tools\tb3_k5_ops.py` returned 0.
  - `python tools\tb3_k5_ops.py status --json` returned current manifest: 28 accepted tasks / 140 accepted trials / no missing Hub URL.
  - `python tools\tb3_k5_ops.py list-remaining --limit 8 --json` returned 46 remaining tasks and a sorted preview.

Important discipline: this helper is for lifecycle/evidence control only. It must not modify official verifier/tests and must not treat started/queued/4-5/public smoke as completion. Use `accept` only after `inspect` reports complete 5/5 green.