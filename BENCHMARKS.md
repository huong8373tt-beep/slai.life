# Benchmark and Run Evidence

This page indexes public Slai Agent Runtime benchmark and run evidence. It distinguishes independent execution records from official leaderboard placement.

## Harbor Hub

- Public profile: <https://hub.harborframework.com/users/huong8373tt-beep/jobs>
- Published records: **155 jobs**
- Coverage includes Terminal-Bench 2.1 and later Terminal-Bench task runs.

Harbor records provide task-level evidence such as job identity, run timing, trials, and reported execution status. Different benchmark versions, task subsets, models, and runtime conditions have different scopes and should not be combined into one leaderboard claim.

## Terminal-Bench 2.1

- Public submission: [harbor-framework/terminal-bench-2-1#217](https://github.com/harbor-framework/terminal-bench-2-1/pull/217)
- Submitted configuration: GPT-5.5 xhigh + Slai Agent Runtime
- Submitted material: 89 tasks × at least K=5, for 445 trials
- Reported infrastructure errors: 0
- Automated static checks: 10/10 passed

The submission received a public review approval and was later closed. Its public timeline does not show a `/judge` result or a public technical finding rejecting the submitted materials.

This is preserved as a public submission and evidence record. It is not represented as an official Terminal-Bench leaderboard placement; leaderboard inclusion is controlled by the benchmark maintainers.

Related archive paths:

```text
benchmarks/terminal-bench/TB2.1/official-submission/
benchmarks/terminal-bench/TB4-0/
```

The TB4 archive includes public Harbor coverage for 63/66 K=5 tasks and separately preserves an older 60-row local manifest snapshot. Those records have different provenance and must not be treated as one identical result set.

## SWE-bench-Live

Public merged submission packages:

- [#28 — Python Lite smoke result](https://github.com/SWE-bench-Live/submission/pull/28)
- [#29 — Python Lite success-only package](https://github.com/SWE-bench-Live/submission/pull/29)
- [#30 — Windows 61 verified-success snapshot](https://github.com/SWE-bench-Live/submission/pull/30)
- [#31 — Python Lite 36/36 update after the XFAIL correction](https://github.com/SWE-bench-Live/submission/pull/31)

During this evaluation work, Slai identified an evaluator-semantic defect and contributed the merged upstream correction:

- [microsoft/SWE-bench-Live#54](https://github.com/microsoft/SWE-bench-Live/pull/54) — pytest `XFAIL` outcomes are handled as expected outcomes instead of being incorrectly classified as failures.

Some submission packages are intentionally smoke, success-only, or staged snapshots. They remain useful, public, and verifiable artifacts, but are not described here as final full-leaderboard results.

Related archive path:

```text
benchmarks/swe-bench-live/
```

## Interpretation

A launched job, a successful local run, a public submission, a merged result package, and official leaderboard inclusion are distinct facts. Public benchmark repositories and maintainers remain authoritative for official display, inclusion, and final evaluation conclusions.