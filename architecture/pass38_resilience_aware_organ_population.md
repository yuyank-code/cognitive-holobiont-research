# Architecture Note — Resilience-Aware Organ Population
**Pass 38 · 2026-11-23**

## Purpose

The original Treatise imagines independent specialist organs whose collective redundancy helps the system survive component failure. New evidence shows that model count, provider count and semantic output diversity are unreliable proxies for independent failure behavior.

The proposed population design therefore separates capability complementarity from response diversity.

## 1. Organ registry

Each registered organ should carry:
- role/capability profile and task-domain evaluation;
- model and training lineage where known;
- prompt, memory, tools, evaluator and harness versions;
- calibration and task-specific reliability;
- known dependencies and failure-mode exposure;
- evidence provenance and permissions;
- measured pairwise and coalition co-failure statistics.

Missing provenance must be marked unknown, not assumed independent.

## 2. Two selection paths

### Complementary-specialist selection
Choose organs that add useful modalities, evidence sources or capabilities. Score by held-out marginal utility, ownership swaps, conditional information and cost. Do not penalize lack of correlation on unrelated tasks.

### Redundant-backup selection
For critical overlapping functions, select backup organs that retain competence while exhibiting different failure responses under matched perturbations. Measure error correlation, same-wrong-answer agreement, calibration dependence and common-mode exposure.

## 3. Dependency-aware immune layer

Maintain a dependency graph spanning:
- base weights, tokenizer, architecture, training data, teacher and alignment;
- system prompts, policies, reward models and evaluators;
- memory stores, retrieval, codecs, bridges and hypernetworks;
- tools, APIs, credentials, infrastructure and orchestration.

Use this graph to design common-mode fault injection and estimate blast radius. It is not a substitute for empirical testing.

## 4. Aggregation

Do not rely on majority vote alone. Use:
- competence-aware weighting;
- provenance and source independence;
- explicit dissent preservation;
- receiver-side evidence checks;
- independent external verification where possible;
- abstention when evidence is correlated or insufficient.

A model evaluating another model may share its blind spots. An evaluator should be treated as another component with its own dependence profile.

## 5. Repair and regeneration

The repair path must be evaluated separately from the organ population. Test whether a failed specialist can be recovered when one or more shared dependencies are compromised:
- hypernetwork/repair generator;
- latent codec/bridge;
- memory and training-data source;
- evaluator and authorization root.

Exact weight reconstruction and capability recovery remain separate outcomes.

## 6. Operating principle

The system should not maximize organ count or a global diversity score. It should maximize task utility and graceful degradation subject to explicit constraints on cost, privacy, reliability, dependency exposure and verification.
