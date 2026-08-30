# Slai Agent Runtime — Terminal-Bench 2.1 Submission Note

This submission was produced by **Slai Agent Runtime**, a proprietary closed-source agent runtime, using the cloud API model configuration shown in the uploaded Harbor jobs.

For this run, the runtime-side model configuration was kept fixed throughout the evaluation: **GPT-5.5 xhigh**. No per-task model switching or model ensemble selection was used by the evaluator.

The result should be interpreted as a system-level agent-runtime result, not as a claim that Slai is a new foundation model. Slai Agent Runtime orchestrated the fixed cloud model API together with local tools, Docker/container execution, long-running task state, environment adaptation, error recovery, and evidence-based verification.

The local evaluation environment and execution harness were set up and adapted by Slai during the run, on a personal machine and home network, while using the official Terminal-Bench 2.1 dataset and Harbor result format.

Human involvement was limited to high-level supervision and scheduling: setting the overall goal, providing runtime resources/API access, issuing continue/wake instructions, and deciding final publication. Humans did not provide per-task solutions, code patches, verifier fixes, or manual result selection.

Acceptance policy: failed or polluted batches were archived and excluded. A task was accepted only after a clean 5/5 batch. The final accepted set contains **89/89 tasks** and **445/445 trials**, all clean 5/5.
