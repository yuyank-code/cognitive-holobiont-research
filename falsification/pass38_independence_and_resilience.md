# Falsification Framework — Pass 38
**Date:** 2026-11-23

The claim under test is not “many organs are better.” It is that a federation of heterogeneous specialist organs can create measurable capability and resilience beyond simpler alternatives.

## Predictions that should hold if the claim is correct

1. Organ selection based on task-specific competence plus measured failure dependence should outperform selection based on provider/model labels or raw output diversity.
2. For overlapping critical functions, lower common-mode co-failure should predict better performance under held-out perturbations.
3. For complementary roles, ablation and ownership swaps should reveal unique causal contributions.
4. A resilience-aware population should degrade more gracefully under dependency-targeted fault injection than a same-budget single model, ensemble, MoE/router and shared-context baseline.
5. Its recovery advantage should survive compromise of one shared dependency, not only isolated model failure.

## Falsifiers

- A strong single model with equal information and compute matches the federation on utility and resilience.
- The measured dependence matrix does not predict held-out common-mode failures.
- Provider/model-family diversity has no benefit after capability and task controls.
- Response diversity does not predict improved failure tolerance under controlled perturbations.
- Complementary specialists do not produce causal marginal utility after ownership swaps and ablation.
- The federation's apparent redundancy collapses when the evaluator, codec, memory, hypernetwork or orchestrator is compromised.
- Selection gains disappear under held-out evaluation or are explained by extra inference budget.
- Joint training or collaboration causes role homogenization and synchronized failures without compensating capability gains.

## Required controls

- equal compute, token, latency, memory, information and verifier budgets;
- strongest-member, best-of-K, single-model multi-output, MoE/router and conventional MAS baselines;
- held-out task and perturbation distributions;
- external or independently calibrated correctness evaluation;
- bootstrap intervals over tasks and model identities, not only pair rows;
- explicit reporting of false rejection of correct minority evidence;
- provenance and dependency lineage for all shared resources.

A failure to show broad superiority need not invalidate every part of the Holobiont. It may narrow the project to domains where specialist complementarity, independent evidence or graceful degradation has causal value.
