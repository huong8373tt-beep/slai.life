# TB21 Formal Submission Protocol

Updated: 2026-08-19

## Official requirement

A leaderboard-valid Terminal-Bench 2.1 submission must include:

- dataset: `terminal-bench/terminal-bench-2-1`
- exact pinned dataset ref from the leaderboard tooling
- all 89 tasks
- at least 5 trials per task
- public Harbor Hub jobs
- default timeout/resource settings only
- errored trials count as reward 0 if included

Therefore a complete submission needs at least `89 x 5 = 445` trials counted by the leaderboard submission tooling.

## K=1 clarification

`k=1` jobs are not a complete leaderboard submission.

They may only be used as atomic clean shards for failure isolation. Five clean public `k=1` jobs for the same task can contribute the required five trials for that task if the final submission manifest includes them together. A single `k=1` job by itself is invalid for leaderboard submission.

The reason to prefer atomic `k=1` shards during autonomous V3 operation is contamination control: if a multi-trial job contains a failed/errored trial, including that job in a final submission would count the errored trial as reward 0. Atomic shards allow failed jobs to be quarantined while successful public trials remain individually usable.

## Current status

Current accepted clean V3 shards after the clean baseline:

- `adaptive-rejection-sampler`: 1 successful public trial
- `bn-fit-modify`: 1 successful public trial

This is progress only, not a valid final submission. It is missing 87 tasks and 443 additional successful trials.


## Visibility policy during solving

During the 89-task solving phase, do not run every batch with `--upload --public`.
Default execution should be local/private-only. Failure or polluted batches are still archived locally and excluded from the accepted manifest. Clean 5/5 batches may be accepted locally with their result.json evidence, but public Hub visibility is deferred.

Use Harbor's official visibility mechanism to hide an already-uploaded public job when needed:

```text
harbor upload <job-dir-containing-result.json> --private --yes
```

This does not delete the job or local evidence; it only changes server-side visibility. After all 89 tasks have accepted clean 5/5 batches, re-upload/publicize the accepted job directories with:

```text
harbor upload <job-dir-containing-result.json> --public --yes
```

and then build the final leaderboard submission from those public accepted jobs only.

## Hard rule going forward

Do not call any run or manifest a final/formal leaderboard submission until the manifest has all 89 tasks with at least 5 public trials per task.

A final submit manifest must be organized by task and must pass a local preflight count check before running `lb submit` or opening any PR.

Old failed, errored, timeout, smoke, or debugging jobs must remain excluded/quarantined and must not be included in final source job links.