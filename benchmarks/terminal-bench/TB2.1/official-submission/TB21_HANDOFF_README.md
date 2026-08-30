# TB21 Slai Submission Handoff README

Last verified locally: 2026-08-22 16:07 +08, after Gmail/GitHub/PR recheck.

## Current external status

There are now two PRs in the official repository:

1. Original user PR:
   - URL: https://github.com/harbor-framework/terminal-bench-2-1/pull/216
   - Title: `Leaderboard Submission: GPT-5.5 xhigh + Slai Agent Runtime`
   - Current state: `CLOSED`
   - Reason: GitHub Actions successfully promoted it into a leaderboard-owned PR.
   - Important bot comment: `Trials cloned and submission promoted to https://github.com/harbor-framework/terminal-bench-2-1/pull/217. Review and merge happen there, this PR stays closed.`

2. Promoted official / leaderboard-owned PR:
   - URL: https://github.com/harbor-framework/terminal-bench-2-1/pull/217
   - Title: `Leaderboard Submission: GPT-5.5 xhigh + Slai Agent Runtime`
   - Current state: `OPEN`
   - Head branch: `harbor-framework:submission/pr-216`
   - Base branch: `main`
   - Mergeability at last check: `MERGEABLE`
   - Review status at last check: `REVIEW_REQUIRED`
   - This is the PR where maintainer review/merge should happen.

Useful PR commands:

```powershell
gh pr view 216 --repo harbor-framework/terminal-bench-2-1 --json number,title,url,state,comments,statusCheckRollup

gh pr view 217 --repo harbor-framework/terminal-bench-2-1 --json number,title,url,state,mergeable,reviewDecision,body,comments,statusCheckRollup,files
```

Open in browser:

```powershell
gh pr view 217 --repo harbor-framework/terminal-bench-2-1 --web
```

## Gmail notification interpretation

The latest GitHub emails are normal and correspond to the PR pipeline:

- Initial `Run failed: Static Analysis` email: old first attempt/first commit failed before the Harbor job config repair.
- Later static analysis email/comment: fixed commit passed.
- `Closed #216` email: expected; PR #216 was closed because the submission was promoted.
- `PR #217` email: expected; this is the promoted leaderboard-owned PR where review/merge now happens.

No immediate user action is required unless GitHub or maintainers ask for changes.

## Static analysis / promoted PR body summary

GitHub Actions reported static analysis PASS:

- 10 checks passed
- 445 trials
- No error: 445
- Accuracy: 100.00%
- Model shown by leaderboard tooling: `GPT-5.5 xhigh [OpenAI]`
- Agent shown by leaderboard tooling: `Slai Agent Runtime [Slai]`

PR #217 body says:

- Promoted from #216
- Trials are cloned into leaderboard-owned copies
- Maintainers can comment `/judge` then `/apply` if they need to recompute metrics with disqualified trajectories

## Harbor public/private status

Final submission jobs are public; unrelated or non-final Harbor jobs were made private.

Verified cleanup summary:

- Formal TB21 public jobs kept public: `89`
- Non-final / unrelated jobs made private: `62`
- Candidate not private after cleanup: `{}`
- Keep jobs not public after cleanup: `{}`

Evidence file:

```text
D:\terminal_bench_slai\runtime\harbor_direct_visibility_verify_20260822_150028.json
```

## Final result audit

Final public audit:

```text
accepted_task_count = 89
accepted_trial_count = 445
public_link_count = 89
validated_clean_5_of_5_count = 89
visibility_summary = {"public": 89}
problems = []
```

Evidence file:

```text
D:\terminal_bench_slai\runtime\tb21_final_public_audit_20260822_134053.json
```

The public link list has 89 non-empty lines:

```text
D:\terminal_bench_slai\runtime\tb21_final_public_submission_links_20260822_134053.txt
```

## Main local files

Root:

```text
D:\terminal_bench_slai\TB21_HANDOFF_README.md
D:\terminal_bench_slai\TB21_SUBMISSION_STATEMENT.md
```

Submission package:

```text
D:\terminal_bench_slai\runtime\tb21_submission_package_20260822_134053.zip
D:\terminal_bench_slai\runtime\tb21_submission_package_20260822_134053\
```

Final audit / links / manifest:

```text
D:\terminal_bench_slai\runtime\tb21_final_public_audit_20260822_134053.json
D:\terminal_bench_slai\runtime\tb21_final_public_submission_links_20260822_134053.txt
D:\terminal_bench_slai\runtime\tb21_final_public_result_summary_20260822_134053.csv
D:\terminal_bench_slai\runtime\tb21_official_k5_submit_manifest.json
D:\terminal_bench_slai\runtime\tb21_final_public_upload_log_20260822_134053.jsonl
D:\terminal_bench_slai\runtime\harbor_direct_visibility_verify_20260822_150028.json
```

PR evidence / submission files:

```text
D:\terminal_bench_slai\runtime\tb21_pr_create_result_20260822_152337.json
D:\terminal_bench_slai\terminal-bench-2-1-main\leaderboard\submissions\2026-08-22-openai-gpt-5-5-xhigh-none-slai-tb-v3-passive-supervisor.json
D:\terminal_bench_slai\runtime\tb21_submission_package_20260822_134053\leaderboard\submissions\2026-08-22-openai-gpt-5-5-xhigh-none-slai-tb-v3-passive-supervisor.json
```

## GitHub fork / branch

Original fork:

```text
https://github.com/huong8373tt-beep/terminal-bench-2-1
```

Original user branch:

```text
submission/2026-08-22-openai-gpt-5-5-xhigh-slai
```

Promoted official branch:

```text
harbor-framework:submission/pr-216
```

Submitted file:

```text
leaderboard/submissions/2026-08-22-openai-gpt-5-5-xhigh-none-slai-tb-v3-passive-supervisor.json
```

## Public explanation / safe wording

Short public description:

> Slai Agent Runtime is a proprietary closed-source agent runtime. The Harbor jobs show the cloud model/API configuration used for the run. This submission used a fixed GPT-5.5 xhigh cloud API configuration on the evaluator side, with no per-task model switching by the evaluator. The result is an agent-runtime result, not a claim that Slai is a new foundation model. Slai set up and adapted the local execution harness on a personal machine and home network using the official Terminal-Bench 2.1 dataset and Harbor result format. Human involvement was limited to high-level supervision, continuation, and final publication decisions, not per-task solving.

Do not publicly release:

- API tokens / credentials
- Internal prompts or memory files
- Private runtime implementation details
- Private caches or dependency bundles unless explicitly reviewed
- Full debug logs from failed/polluted batches
- Local absolute paths unless necessary and safe

## What to do next

1. Watch PR #217, not PR #216.
2. Do not reopen PR #216; it is intentionally closed after promotion.
3. If maintainers ask for details, send the short explanation and the 89 public Harbor links.
4. If maintainers ask for package, use:
   `D:\terminal_bench_slai\runtime\tb21_submission_package_20260822_134053.zip`
5. If maintainers ask for a rerun or official maintainer-run, point to PR #217 plus the public Harbor jobs and offer the sanitized package.
6. Do not rerun, delete, or overwrite the accepted K5 job directories unless there is a clear need and a backup exists.

## Disaster recovery plan

Recommended backups:

- Full workspace mirror/copy exists or should exist at:
  `E:\terminal_bench_slai`
- Small critical recovery package should exist at:
  `E:\terminal_bench_slai_tb21_dr_20260822`
- Small critical recovery zip should exist at:
  `E:\terminal_bench_slai_tb21_dr_20260822.zip`

The small DR package is enough to reconstruct the public submission, PR context, audit summary, and maintainer communication without copying every heavy job directory.

## One-line status

TB21 Slai submission is externally visible: 89 public Harbor jobs, original PR #216 closed after successful promotion, promoted PR #217 open/mergeable/review-required, static analysis pass, waiting for maintainer review/merge.