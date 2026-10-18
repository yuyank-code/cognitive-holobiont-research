# Source Ledger — Pass 29 (2026-10-19)

## HiddenBench / distributed-information reasoning
- Li, Naito, Shirado, *Systematic Failures in Collective Reasoning under Distributed Information in Multi-Agent LLMs*.
- Status: peer-reviewed ICML 2026, PMLR 306.
- Paper: https://proceedings.mlr.press/v306/li26ej.html
- Public code/data: https://github.com/Yassellee/HiddenBench_ICML
- Evidence: 65 Hidden Profile tasks; 15 frontier models; 30.1% multi-agent accuracy under distributed information vs 80.7% for a single agent with complete information; structured protocol helps.
- Limits: full-profile baseline is privileged; task generation deliberately isolates information-discovery difficulty; figures are benchmark-specific.

## MemRiskBench
- Jiang, Yuan, Li, *MemRiskBench: Trace-Aware Risk-Preserving Evaluation for Long-Horizon LLM Agents*.
- Status: arXiv preprint, 2026-09-14. Paper: https://arxiv.org/abs/2609.14976
- Evidence: 120 scripted episodes; five scored memory-risk classes plus documented but unscored summary contamination; deterministic trace scoring; five local quantized models; per-risk differences; risk-preserving subset selector.
- Limits: small scripted benchmark; model-risk contrasts do not survive Holm correction; expected-value audit changed 39/600 scores; refusal semantics affect scores; selector depends on reference models.
- Related capability benchmark: LongMemEval, https://arxiv.org/abs/2410.10813 — 500 questions covering extraction, multi-session reasoning, temporal reasoning, knowledge updates, and abstention.

## MAESTRO
- Ma et al., *MAESTRO: Multi-Agent Evaluation Suite for Testing, Reliability, and Observability*.
- Status: open arXiv preprint, 2026-01-01. Paper: https://arxiv.org/abs/2601.00481
- Code: https://github.com/sands-lab/maestro
- Evidence: 12 representative MAS; repeated runs/backends/tool settings; architecture-dependent resources and reproducibility; stable structure with temporal variation; 75.17% silent semantic failures in its own categorized failure collection.
- Limits: sampled architectures; study-specific failure composition; LLM judge attribution is fallible.

## The Illusion of Multi-Agent Advantage
- Jwalapuram et al., *The Illusion of Multi-Agent Advantage*.
- Status: arXiv preprint, 2026-06-11. Paper: https://arxiv.org/abs/2606.13003
- Evidence: some automatically generated MAS underperform CoT plus self-consistency at up to 10x cost; expert-designed MAS outperform on a synthetic task with explicit decomposition/context separation/parallelization.
- Limits: selected tasks and baselines; synthetic task intentionally favors decomposition; not evidence of universal MAS inferiority.

## Not All Flips Are Conformity
- Hao et al., *Not All Flips Are Conformity: Decomposing Stance Convergence in Multi-Agent LLM Debate*.
- Status: arXiv preprint, 2026-05-30. Paper: https://arxiv.org/abs/2606.00820
- Evidence: separates self-reflection instability, stance-only conformity, and reasoning-induced change; reports 37% self-reflection answer changes and 29% strict conformity in primary setting.
- Limits: model/task-specific; reducing peer adoption can block beneficial influence as well as harmful influence.

## CoFi-PGMA
- Tong and Ben-Gal, *CoFi-PGMA: Counterfactual Policy Gradients under Filtered Feedback for Multi-Agent LLMs*.
- Status: arXiv preprint. Paper: https://arxiv.org/abs/2604.22785
- Evidence: system reward may not identify individual causal contribution; contribution is coalition-dependent; reported GRPO experiment on GSM8K.
- Limits: credit-assignment/training paper, not direct validation of Holobiont architecture; narrow experimental scope.

## Evidence discipline
Distinguish peer-reviewed work from preprints; separate oracle from access-matched baselines; preserve null/negative results; report per-risk outcomes; audit deterministic scorers; use randomized interventions for causal claims; account for resource and information differences.
