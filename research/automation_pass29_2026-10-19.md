# Cognitive Holobiont Research — Pass 29
**Date:** 2026-10-19

## Executive result
This pass connects collective information acquisition, execution-level reliability, debate counterfactuals, and long-horizon memory safety. The central conclusion is methodological: a collective architecture cannot be credibly optimized until information flows, execution traces, and risk-specific failures are observable, and contribution claims are tested with counterfactuals. The originating Treatise/PDF remains a hypothesis/specification, not established fact.

## 1. HiddenBench: distributed facts are not automatically collective knowledge
Li, Naito, and Shirado's peer-reviewed ICML 2026 paper introduces 65 Hidden Profile tasks and evaluates 15 frontier models. It reports 30.1% accuracy for multi-agent systems under distributed information versus 80.7% for a single agent with the complete profile. Agents often fail to infer that teammates may hold unexpressed decisive facts and converge prematurely on shared evidence. A lightweight structured communication protocol improves results across model families.

Paper: https://proceedings.mlr.press/v306/li26ej.html
Public benchmark/code: https://github.com/Yassellee/HiddenBench_ICML

The full-profile single-agent condition is a privileged-information diagnostic or upper bound, not an access-matched deployment baseline. It shows information-access headroom but does not isolate the causal benefit of multi-agent communication. The benchmark's task generation intentionally isolates collective information exploration, which improves diagnostic focus but limits ecological generalization. These percentages are benchmark-specific.

**Implication:** evaluate information acquisition, authorized transmission, and integration separately. Include an access-matched single-agent baseline, label full-information oracles as upper bounds, and randomize decisive-information ownership. Asking/elicitation must be tested separately from broadcasting.

## 2. MemRiskBench: aggregate success can hide severe memory risk
The September 2026 preprint proposes 120 scripted episodes, deterministic trace-grounded checks, and five scored risks: stale-memory reliance, conflict misresolution, cross-scope leakage, revoked-memory reuse, and constraint decay. Summary contamination is documented as a sixth risk but not integrated into the main score. Five local quantized models from 1.5B to 7B parameters are tested.

Paper: https://arxiv.org/abs/2609.14976
Complementary capability benchmark, LongMemEval: https://arxiv.org/abs/2410.10813

MemRiskBench reports aggregate task-success scores from 0.775 to 0.885, but cross-scope leakage checks have only 1/24 to 10/24 passes across models (about 4%–42%), while explicit constraint checks range from 21/24 to 24/24 (88%–100%). Aggregate success can conceal a severe risk-specific weakness.

Limits: the benchmark is small/scripted and uses local quantized models; it is not a production prevalence estimate. Pairwise model differences across 50 model-risk comparisons do not survive the stated Holm correction, so do not infer a model-size trend. A scoring audit changed 39 of 600 trace-episode scores after expected values for 20 episodes were revised. Deterministic scoring can still be wrong when its specification is faulty. Refusal semantics also differ between default and safety-aware variants. Its risk-preserving 20% subset selector reports strong ranking/risk coverage on its reference set, but its features depend on that reference set and do not guarantee generalization to unseen models.

LongMemEval tests extraction, multi-session reasoning, temporal reasoning, knowledge updates, and abstention. Capability-oriented memory tests and harm-oriented risk tests are complementary, not interchangeable.

**Implication:** measure memory utility and memory-induced risk separately. Report per-risk rates, severity, exposure opportunities, and benign false rejection. Preserve risk coverage when compressing benchmarks; ranking fidelity alone is insufficient.

## 3. MAESTRO: execution observability is necessary
The open preprint MAESTRO instruments 12 representative multi-agent systems across repeated runs, backends, and tool settings.

Paper: https://arxiv.org/abs/2601.00481
Code: https://github.com/sands-lab/maestro

It reports relatively stable call-graph structure alongside temporal variation in actual call sequences and outcomes. Architecture strongly shapes resource profiles, reproducibility, and cost-latency-accuracy trade-offs. In its experimental collection, 75.17% of categorized failures are silent semantic failures—plausible but unusable outputs, not explicit exceptions. This is a study-specific percentage, not a population estimate. The paper also reports disagreement among LLM judges in failure attribution. A trace can reveal where a failure occurred without proving which component caused it.

**Implication:** collect execution telemetry and independently verify outcomes. Use traces to generate causal hypotheses, then test them with interventions.

## 4. Complexity is not architectural value
The 2026 preprint The Illusion of Multi-Agent Advantage reports that automatically generated MAS underperform single-agent chain-of-thought plus self-consistency on evaluated reasoning and interactive workflows, sometimes at up to ten times the cost. On a synthetic task deliberately designed around decomposition, context separation, and parallelization, expert-designed MAS outperform automatic architectures.

Paper: https://arxiv.org/abs/2606.13003

This does not prove that MAS are generally inferior. It shows that a task may contain genuine parallelism while a particular workflow fails to exploit it. Compare strong single-agent and expert-designed multi-agent baselines.

## 5. Debate needs counterfactual controls
The preprint Not All Flips Are Conformity separates spontaneous self-revision, stance-only conformity, and reasoning-induced persuasion. In its primary MMLU-Pro setting, 37% of agent-question observations changed during isolated self-reflection; strict conformity was reported at 29%, with 57%–77% of strict conformity transitions across reported model replications being correct-to-wrong.

Paper: https://arxiv.org/abs/2606.00820

These rates are task/model-specific. Raw answer flips do not identify peer-caused learning. Use independent initial answers, self-reflection without peer information, stance-only exposure, full-rationale exposure, and external outcome verification. Report beneficial and harmful transitions separately.

## 6. Contribution depends on the coalition
The preprint CoFi-PGMA argues that system reward alone cannot identify individual causal contribution and that an agent's marginal contribution depends on which other agents are present. It reports a GRPO instantiation on GSM8K.

Paper: https://arxiv.org/abs/2604.22785

This is a credit-assignment paper, not direct validation of the Holobiont. Leave-one-agent-out tests are useful but may miss higher-order interactions; sampled coalition interventions should report uncertainty.

## 7. Architecture hypothesis: observability before adaptivity
Proposed, not yet implemented: maintain two linked ledgers.

**Epistemic ledger:** claim/fact ID, source/provenance, agent access, timestamp/validity, supersession or revocation, dependencies, evidence dependence, authorization and disclosure scope.

**Execution ledger:** task/run IDs, model/agent version and role, inputs visible to each agent, messages and protocol decisions, memory reads/writes and versions, tool calls/results/retries, termination, token/compute/latency/cost, independent outcome checks, and risk-specific violations.

Link the ledgers by stable identifiers. A message graph is not proof of truth, and privacy-sensitive content must remain scoped and access-controlled. Observability does not justify indiscriminate retention of private reasoning.

## 8. Falsification framework
Compare strong single-agent multi-output/self-consistency, independent heterogeneous ensembles, conventional and expert-designed MAS, shared-context/task-queue systems, adaptive routing, and full-information oracles labelled as upper bounds.

Across hidden-profile reasoning, decomposable workflows, long-horizon memory, and state-changing tool use: match information access and total resource budgets; randomize information ownership, agent identity, message exposure, and protocol/topology; run multiple seeds; report paired uncertainty; verify outcomes independently; test scorers with mutations; and report memory-risk categories separately. Measure utility, decisive facts recovered, harmful/beneficial answer changes, latency, tokens, tools, memory, verification, and recovery.

Reject Holobiont-specific synergy if gains vanish against access- and resource-matched baselines, fail ownership swaps or held-out tasks, depend on oracle information, violate hard risk limits, or rest on observational trace attribution.

## Conclusion
Evidence supports explicit elicitation, task-aligned architecture, execution observability, and risk-specific memory governance in bounded settings. Naive interaction, automatic orchestration, and aggregate-only evaluation can mislead. Universal latent language, recovery of unique capabilities after all information is lost, task-general positive coalition synergy, unrestricted safe self-rearchitecture, and machine consciousness remain unvalidated. No implementation is recommended.
