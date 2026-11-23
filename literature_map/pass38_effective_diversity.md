# Living Literature Map — Pass 38: Effective Diversity and Common-Mode Failure
**Date:** 2026-11-23

## Research cluster A — Correlated correctness and effective ensemble size

- Morante & Romero García-Rubio (Discover Informatics, 2026): variance-based effective voter count and task-specific correlation measurement.
- Kim et al. (ICML 2025): large-scale correlated-error study across >350 LLMs.
- Goel et al. (ICML 2025): CAPA and model similarity effects on AI oversight.

Open gap: move from binary answer correctness to structured outputs, multi-step plans, tools, multimodal observations and long-horizon actions.

## Research cluster B — Measuring behavioral/process diversity

- Tieman & Markou (arXiv 2026): permutation-controlled NCD residual predicts correlated wrong-answer agreement.
- Donghwan Kim (arXiv 2026): capability-controlled audit of five diversity metrics and majority-vote gain.
- Artificial Hivemind (2025): semantic homogeneity in open-ended model outputs.

Open gap: evaluate model + prompt + memory + tool + evaluator + harness configurations, not only bare model outputs. Test whether the metric predicts failure under controlled interventions.

## Research cluster C — Error shaping and selection

- D-FUSEr (ICML 2026): diverse-failure reward and anti-votes.
- CoRE (Findings EACL 2026): token- and model-level consistency filtering for ensemble outputs.

Open gap: separate error-distribution shaping from capability loss, and test under adversarial, distribution-shift and minority-evidence conditions.

## Research cluster D — Complementary private information

- HiddenBench (ICML 2026): collective information elicitation failure and structured protocol improvement.

Open gap: combine private-evidence tasks with model-family and failure-dependence interventions. A group can have complementary knowledge without knowing how to request it.

## Research cluster E — Byzantine and common-mode robustness

- SAC (arXiv 2026): receiver-side filtering and graph robustness.
- CP-WBFT (AAAI 2026): confidence-probe weighted Byzantine fault-tolerance method.

Open gap: evaluator correlation, shared model lineage, shared codec/hypernetwork, adaptive adversaries, dynamic topologies and long-horizon memory propagation.

## Project-specific synthesis

The Holobiont requires two distinct selection objectives:
1. complementary organs that add capabilities or private evidence;
2. response-diverse backups for overlapping critical functions.

It also needs dependency provenance so that apparently different organs are not treated as independent when they share a compromised evaluator, memory, bridge, training source or toolchain.
