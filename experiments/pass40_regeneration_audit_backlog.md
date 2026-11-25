# Experiment Backlog — Pass 40
**Date:** 2026-11-25  
**Priority:** Distinguish peer-assisted regeneration from repair, backup, adapter learning, merging and teacher distillation.

## Experiment 1 — Capability deletion and information-survival matrix

**Question:** Can surviving organs recover a specialist after its own artifacts are removed?

1. Train or select a specialist with a measurable capability gap over the generalist fallback.
2. Create a hidden capability manifest with common, rare, OOD, adversarial, calibration and safety slices.
3. Preserve the original specialist in an offline evaluator vault inaccessible to recovery.
4. Randomize removal of specialist weights, adapters, base checkpoint, domain data, labels, teacher/API access, raw trajectories, hidden-state/KV traces, gradients/task vectors and organ memory.
5. Permit only declared surviving organs and recovery components to act.
6. Evaluate functional recovery, not only weight similarity.

**Controls:** no-information, wrong-information, generalist fallback, backup restore, retrieval, procedural adapter, merge, peer distillation and full retraining on surviving data.

## Experiment 2 — HyperRepair boundary replication

Replicate the published HyperRepair setting first, preserving its assumptions:
- target fine-tuned model survives;
- shared base-family lineage is known;
- source repair examples and general training data are available;
- target-domain examples are absent at deployment.

Then progressively remove:
A. target activation fingerprint reference/base model;
B. source repair examples;
C. hypernetwork training domains;
D. same-family assumption;
E. target fine-tuned checkpoint.

This maps the exact boundary between post-hoc repair and genuine regeneration.

## Experiment 3 — Peer-to-peer behavioral distillation

Give the recovery coalition access to:
- surviving peer weights only;
- peer answers on a fixed query budget;
- peer reasoning/trajectory records;
- structured evidence records;
- latent/KV traces where permitted;
- combinations of these sources.

Compare with a compute-matched generalist generating its own training data. Keep a private target capability split inaccessible to both recovery and peers. Measure whether peer-specific knowledge, rather than generic public knowledge, explains the gain.

## Experiment 4 — Procedural repair vs. capability reconstruction

Compare Self-Direction-style adapters, Skills.md, retrieval, ordinary reflection, and full specialist retraining. Separate recurring tool procedure recovery from domain knowledge, reasoning, calibration and multimodal skill. Include router false-positive and wrong-adapter tests.

## Experiment 5 — Specialist merge under deletion and interference

Use a shared-base specialist family. Compare plain averaging, TIES/DARE-style baselines and PRISM. Then remove one specialist checkpoint before merging. Determine whether any claimed recovery is possible from remaining specialists alone and identify which task slices are lost.

## Experiment 6 — Long-horizon plasticity and repair drift

Apply repeated adaptation and repair cycles. Track:
- old capability retention;
- future-task learning speed;
- feature effective rank/plasticity;
- calibration;
- adapter interference;
- hypernetwork output drift;
- common-mode errors across generated specialists.

Include a reset/reinitialize control and a frozen-base-plus-residual control.

## Experiment 7 — Recovery under compromised DNA

Corrupt the repair hypernetwork, its training examples, its evaluator or its shared latent codec independently and jointly. Test whether a diverse second repair route can detect and bypass the compromised generator.

## Minimum reporting

Every run must publish:
- exact deletion manifest;
- surviving-information manifest;
- data/model/adapter hashes and lineage;
- total compute, latency, storage and data access;
- per-slice capability scores and confidence intervals;
- recovery ratio against the strongest fallback;
- rare/OOD/adversarial/safety results;
- rollback and reintegration outcomes.
