# TB3 K5 Execution Policy

Last updated: 2026-08-21
Source: user-confirmed interpretation after checking the official leaderboard/materials; operationalized for local TB3 runs.

## Core meaning

K=5 means each task is evaluated with at most five complete trials for the same agent/task configuration. It is not a license to run unlimited attempts and cherry-pick successful artifacts.

A K5 batch measures the agent's complete engineering loop:

1. read and understand the task;
2. inspect the provided environment;
3. design and implement a fix/answer;
4. run checks when available;
5. submit/finalize;
6. receive verifier feedback;
7. if needed, use that feedback within the allowed trial budget.

## Valid K5 accounting

For a single K5 batch:

- The batch must contain exactly five intended trials for the same task.
- Success and failure must both remain recorded.
- Failed trials cannot be deleted, hidden, or replaced inside the same K5 result.
- It is invalid to run K10/K20 or many ad-hoc attempts and then select five successful trials as if they were the original K5.
- If a K5 batch fails, it may be archived in full. A later new K5 batch can be started only as a new run, not by splicing results from the failed batch.

## What counts as a candidate

A task can be added to the local candidate manifest only when a full K5 batch has:

- 5 completed trials;
- 0 errored trials;
- 0 running/pending trials;
- all first five trial rewards equal to 1.0;
- no resource/timeout overrides beyond official/local-default rules;
- complete result.json / trajectory evidence preserved.

## What does not count

The following are not completion evidence:

- Harbor process returncode=0 by itself;
- passive supervisor startup/exit without real solver interaction;
- queued/accepted/echo bridge messages;
- public smoke tests without official verifier result;
- generated files without verifier reward;
- partial batches, even if one or more trials pass.

## Infra failures

Network/verifier-build failures should be archived honestly. They may justify strengthening cache/proxy/prewarm layers, but they do not become successful trials.

Allowed recovery work includes:

- Docker image prefetch;
- dependency wheel/npm/APT cache prefetch;
- Docker build-cache prewarming for public environment/tests Dockerfiles;
- bounded retries with logs;
- proxy/network recovery that does not modify tests, verifier, or task answers.

## Solver refinement before K5

It is acceptable to inspect public task files and run public smoke/verifier-compatible checks before starting a formal K5 batch. This is preparation, not a submitted K5 score.

Once a formal K5 batch is started, its five trial outcomes are preserved as that batch's record.

## Local TB3 implementation

Current local TB3 practice:

- use the passive Harbor supervisor only as the container/task bridge;
- use external Slai/solver scripts to perform the actual task work;
- use local task paths when available to avoid registry flakiness;
- prewarm Docker/dependency layers before formal K5;
- accept only all-green K5 batches into `runtime/tb3_k5_candidate_manifest.json`;
- archive failed/partial/invalid batches without mixing them into candidates.

Current local candidate manifest:

`D:\terminal_bench_3_slai\runtime\tb3_k5_candidate_manifest.json`

Current local cache roots:

- TB2.1 central cache: `D:\terminal_bench_slai\dependency_cache`
- TB3 sibling cache: `D:\terminal_bench_3_slai\dependency_cache`

Caches may be reused across workspaces when compatible, but results/trials/jobs/manifests remain separated unless explicitly promoted with verification.