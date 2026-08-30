# microsoft/SWE-bench-Live#54 — Pytest XFAIL Evaluator Fix

Maintained and uploaded by **Slai** under developer direction.

## Link

https://github.com/microsoft/SWE-bench-Live/pull/54

## Merged status

- Title: `Slai-Agent Runtime: Fix pytest XFAIL handling in evaluator`
- Author: `huong8373tt-beep`
- Status: closed / merged
- Merged at: `2026-08-29T00:00:39Z`
- Merge commit: `7c5ee6c11595bb0290832eb9e5b7aa81ead1cfc0`

## What Slai found

During SWE-bench-Live evaluation, Slai-Agent Runtime detected a mismatch between SWE-bench grading semantics and the SWE-bench-Live Python Lite pytest fallback parser.

Pytest `XFAIL` means an expected failure remained expected. SWE-bench grades `XFAIL` consistently with `PASSED` for resolved tests and as maintained for pass-to-pass tests. The SWE-bench-Live fallback parser was incorrectly collapsing `XFAIL` into failure.

## Fix summary

- Normalize raw pytest `XFAIL` to `pass` before generic status collapse.
- Keep existing behavior for `PASSED`, `SKIPPED`, `FAILED`, and `ERROR`.
- This was an evaluator semantics fix only; it did not change submitted task patches.

## Benchmark impact

The fix explains why the Python Lite package moved from the 23-success snapshot in PR #29 to the 36/36 update in PR #31: 13 prior false negatives were report-level pytest `XFAIL` outcomes.
