# Experiment Backlog — Pass 38
**Date:** 2026-11-23

## E38-1 — Organ Independence Audit (highest priority)

**Question:** How many genuinely different failure responses does the candidate organ pool contain?

Conditions:
- same model sampled repeatedly;
- same model with persona/role prompts;
- models from one family;
- models from different providers/families;
- separately trained or differently distilled specialists where provenance permits;
- different tools/evaluators/harnesses for the same underlying models.

Measure per task family:
- individual accuracy and calibration;
- pairwise correctness/error correlation;
- same-wrong-answer agreement corrected for chance;
- response/process diversity metrics;
- effective sample size with bootstrap intervals;
- cost and latency.

Do not collapse all metrics into one score.

## E38-2 — Capability-controlled selection

Build candidate ensembles and compare:
- strongest member;
- equal-weight majority/plurality;
- competence-weighted aggregation;
- learned selector/router;
- best-of-K;
- single-model multi-output;
- independent external verifier.

Use train/validation/test splits for selection. Evaluate gain over the strongest member on held-out tasks. Control for mean and best member capability, capability gap, parse rate and cost.

## E38-3 — Functional complementarity and ownership swaps

Partition evidence across organs. Randomize which organ receives which evidence while keeping model weights and roles fixed. Compare:
- private evidence, no communication;
- structured evidence exchange;
- targeted elicitation;
- full evidence union in one model;
- equal-token compressed evidence union;
- best-of-K and learned routing.

Measure marginal utility by organ ablation and ownership swaps. This prevents confusing model identity with evidence ownership.

## E38-4 — Response diversity under common perturbations

Apply matched perturbations to organs with overlapping roles:
- adversarial prompt injection;
- distribution shift;
- misleading but plausible evidence;
- tool/API corruption;
- truncated or stale messages;
- evaluator miscalibration;
- memory poisoning.

Estimate whether response-diversity metrics predict graceful degradation on held-out perturbations.

## E38-5 — Dependency graph and common-mode injection

Independently and jointly compromise:
- shared base checkpoint or teacher;
- training-data source;
- system prompt/policy template;
- judge/evaluator;
- shared memory/retrieval index;
- latent codec/bridge;
- hypernetwork/repair generator;
- tool provider/credentials;
- orchestrator and routing metadata.

Compare a diverse-model federation with a single-model baseline, ensemble, MoE/router and shared-context architecture.

## E38-6 — Longitudinal homogenization

Run repeated collaboration and/or joint adaptation. Measure capability profiles, pairwise failure correlations, dissent retention, unique evidence contribution and common-mode vulnerabilities over time. Include a no-interaction control and a role-specialization control.

## E38-7 — Repair under correlated compromise

Remove one organ and separately corrupt its:
- checkpoint;
- private data;
- bridge/codec;
- hypernetwork;
- shared memory lineage;
- evaluator.

Compare repair from surviving organs against checkpoint restore, adapter restore, distillation, retraining and external replacement. Score exact-weight recovery separately from capability recovery.

## Required reporting

Report confidence intervals, task-specific matrices, bootstrap unit, model lineage/provenance where known, total compute/tokens/latency/bandwidth, verifier budget, failure-injection coverage, benign false rejection, privacy leakage and recovery quality.
