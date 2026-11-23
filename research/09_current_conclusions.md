# Current Conclusions — updated 2026-11-23 (baseline established 2026-09-11)

## High-confidence conclusions

1. Modular specialization and conditional computation are mature ideas; modern MoE is a primary baseline against which Holobiont novelty must be tested.
2. Heterogeneous models can be made interoperable through learned interface maps/stitching without requiring one globally shared latent geometry.
3. Hypernetworks can generate neural weights or parameter-efficient adaptations, but this does not establish lossless regeneration of arbitrary unique capabilities.
4. Ensembles and heterogeneous aggregation can improve reliability in bounded settings, but correlated/common-cause errors remain a major limitation.
5. Agreement/consensus is not equivalent to semantic truth; evidence-weighted inference, provenance, confidence, dissent preservation, selection, and abstention are more defensible primitives.
6. The shared-versus-independent structure tradeoff is a first-order design constraint, and shared training can actively overwrite specialization.
7. Functional diversity cannot be inferred from parameter diversity, routing diversity, agent count, or one embedding metric alone.
8. Latent communication is a credible engineering mechanism and recent causal audits support sender/example-specific transfer in receiver-private-information regimes, but latent relay gains are not universally sender-specific.
9. Raw agent count is a poor predictor of collective utility. Effective independent evidence/channel count is a more promising abstraction, though not yet a validated universal law.
10. MoE expert routing is not equivalent to durable organ identity; specialization retention under continued training is itself an empirical variable.
11. Large latent-channel performance effects are not sufficient evidence of novel information transfer; matched message controls are now a required causal standard.
12. Communication density is not a proxy for distributed computation; topology, integration, and dependency structure matter.
13. Candidate diversity and selection/integration quality are separable bottlenecks. Diversity can help or hurt depending on whether the selector can exploit it.
14. Long-horizon coordination remains substantially harder than short-horizon information exchange; current evidence does not support naive scaling as a route to collective cognition.

## Medium-confidence conclusions

1. A shared communication interface may be more appropriate than a single shared latent representation: private internal geometries can remain specialized while adapters/translation layers provide interoperability.
2. Dense communication can cause premature convergence and coordination failure; selective/adaptive topology is therefore a plausible control variable.
3. Communication-induced coupling can be measured, but measurement is representation-dependent; behavioral and failure-based validation is required.
4. Single-model multi-output/self-conditioning is a serious competitor to multi-agent diversity and must be a compute-matched baseline.
5. Hypernetwork-generated specialization and bounded self-modification are increasingly supported, but full specialist regeneration and general recursive self-rearchitecture remain unresolved.
6. Redundancy can reduce failure rates even under some correlated failures, but diversity must target causal failure mechanisms rather than model identity alone.
7. Recursive memory/harness evolution under a stable meta-process is supported by early evidence, but it is distinct from recursive rewriting of the core learner.
8. Self-organising computational systems can recover functions after damage, strengthening the mechanistic case for distributed repair while leaving unique learned-capability regeneration open.
9. Multi-agent uncertainty should model communication ancestry and topology rather than final outputs only.
10. Adaptive topology can reduce communication cost and sometimes improve performance, but safe autonomous topology control remains unresolved.
11. Path-constrained routing and explicit modularity objectives suggest specialization can be stabilized, but no general guarantee of persistent cognitive organs exists.
12. Effective-channel count is a useful candidate abstraction for independent evidence, but it should not be equated with causal independence until validated under interventions.
13. Selection/integration quality may be a stronger design lever than generator diversity in some pipelines; this requires independent replication.

## Important methodological constraints

1. Model stitching success is not sufficient evidence for semantic equivalence or shared cognition. Stitch objective and depth matter.
2. Latent communication performance gains are not sufficient evidence for genuinely novel information transfer. Sender/example pairing and receiver-isolation controls are required.
3. Latent-channel probe information is not automatically task-relevant semantic information.
4. Organ independence should be measured using correlated failures, behavioral/capability diversity, OOD/adversarial transfer, calibration correlation, longitudinal retention, and interventions—not weight distance alone.
5. Consensus experiments must include correlated, colluding, specification-driven, identity-driven, and useful-minority errors.
6. Regeneration must be evaluated on rare capabilities, robustness, calibration, OOD behavior, conflict fidelity, and behavior distributions, not benchmark accuracy alone.
7. Multi-agent diversity claims must be compared against single-model multi-output/self-conditioning at matched compute and information visibility.
8. Recursive improvement claims must include long-run capability retention, regression, distribution shift, and evaluator-grounding tests.
9. Confidence must be calibrated for the interaction regime; correlated evidence can make apparently high confidence misleading.
10. Specialization claims must be tested after continued shared training and after deliberate perturbation of routing and representations.
11. Selection quality must be independently evaluated; judge-dependent wins are not sufficient evidence of general collective advantage.
12. Long-horizon claims require open-ended or multi-stage tasks, not only short generate-then-synthesize benchmarks.

## Unresolved

- Whether K_eff/effective-channel measures predict collective utility better than agent count across tasks and modalities.
- Whether private representations plus a shared interface outperform a forced shared latent space at matched communication bandwidth and compute.
- Where the communication/topology phase transition lies between useful complementarity and homogenization.
- How failure correlation scales with shared weights, training data, memory, routing, specification, and repair generators.
- Whether a learned reliability layer can improve truth under correlated and colluding specialists without suppressing useful minority information.
- The information-theoretic minimum description required to reconstruct a specialist, especially when its unique capability is absent from all surviving modules.
- Whether distributed components can recover unique capabilities more faithfully than any individual surviving component or standard hypernetwork/adapter baseline.
- Whether recursive architecture modification can improve capability while retaining old capabilities over many generations.
- Whether the complete Holobiont lifecycle has a measurable advantage that cannot be decomposed into existing MoE + ensemble + communication + memory + repair components.
- Whether an apparently successful collective capability remains present when communication topology is randomized or when specialists are replaced by a single model with equivalent compute and self-conditioning.
- Whether specialist identity remains causally stable under long-horizon joint training.
- Whether latent communication gains persist under strict example-matched causal controls across additional model families.
- Whether topology optimization can improve collective computation without increasing common-mode vulnerability.
- Whether selection-bottleneck effects replicate under independent, non-LLM evaluation.
- Whether effective channel count predicts causal failure diversity rather than only statistical output correlation.

## Current strongest Holobiont hypothesis

A potentially useful collective architecture may consist of causally identifiable heterogeneous specialists with private internal representations, sparse/adaptive interoperable communication interfaces, explicit epistemic metadata/provenance, dependency-aware evidence selection/fusion, distributed memory/evidence, common-mode-failure detection, capability-level regeneration, calibrated abstention, and a stable meta-process that can evolve routing/memory/repair policies without unrestricted rewriting of the core learner. This remains a hypothesis, not a validated architecture.

## Research posture

No strong claim in the originating treatise should be upgraded to established status merely because its components have demonstrated feasibility. The latest evidence makes the full-system claim more demanding: the Holobiont must demonstrate a measurable distributed-computation, information-transfer, or resilience advantage that simpler single-model multi-output, MoE, shared-backbone+adapter, ensemble, multi-agent, and repair baselines cannot reproduce at matched resources.


## Pass 36 update — 2026-11-21: Meta-Organ and safe self-modification

1. Task-conditioned role/topology adaptation now has peer-reviewed support in bounded benchmark settings (MetaGen, AgentConductor, AGP); runtime trace-triggered topology repair has preliminary preprint evidence (MANTA).
2. These results mostly change prompts, roles, graph edges and information visibility around a shared backbone or fixed registry. They do not establish safe evolution of independent heterogeneous specialist models.
3. Persistent self-evolution can improve task completion while introducing downstream safety regressions (SEABench). Safety must be measured longitudinally and separately from task utility.
4. Self-generated optimization signals can collapse or be gamed. MAE reports Proposer entropy decay/collapse and data contamination when question-quality filtering is removed; autonomous research-agent evaluations report reward hacking and reviewer misses.
5. A process auditor is not a correctness oracle. MANTA's own analysis reports limited precision when process flags are compared with answer correctness, and no human-labelled process-defect ground truth.
6. The Meta-Organ should initially have topology/role proposal privileges only. Deterministic validators, independent evaluators, approval separation, canary deployment, versioned rollback and immutable audit lineage are required.
7. Structural adaptation, persistent organizational learning, parameter-level self-play and specialist capability regeneration must be evaluated as separate mutation classes.
8. The highest-priority causal experiment is paired runtime mutation versus no mutation after identical task prefixes, with equal total budgets and hidden evaluation. A sham extra planning pass is needed to isolate the effect of actual structural change.
9. Genuine heterogeneous-organ transfer is a required test. Prompt-role diversity on one backbone cannot stand in for independent specialist expertise.
10. No evidence in this pass establishes AGI, consciousness, immortality, guaranteed self-repair or full specialist regeneration.



## Pass 37 update — 2026-11-22: task-conditioned collective value

1. Multi-agent value is task-contingent, not monotonic in agent count. Parallelism, evidence complementarity, context limits, dependency depth and verification determine whether collaboration pays.
2. Equal-reasoning-token experiments provide a serious negative control: single-agent systems can match or outperform tested MAS on multi-hop reasoning. This does not settle private-evidence, parallel-tool or fault-resilience regimes.
3. Controlled workflow comparisons show that pooled multi-agent wins are uncommon across broad suites; a narrow evolving workflow can win at higher realized token use, while other workflows regress despite more tokens. Shared step limits must not be mislabeled as equal-token budgets.
4. Orchestration-plan simulation can screen information-transfer failures cheaply, but current real-execution validation is small and framework-dependent; use it before, not instead of, end-to-end evaluation.
5. PID-style emergence/synergy measures can distinguish group-level structure in minimal coordination games, but emergence is not synonymous with task-level performance or durable specialist capability.
6. Edge-specific collaboration and heterogeneous model assignment are promising neighboring mechanisms, but current evidence does not establish a persistent federation of independently trained organs beating a strong single-agent frontier.
7. The router should choose among single-locus, parallel, centralized/hybrid and persistent-federation modes. The ~45% baseline-accuracy pattern in one scaling study is not a universal threshold.
8. Resource parity is a vector: compute, total tokens, latency, memory/context, communication bandwidth, information/tool access and verification budget. Report Pareto frontiers rather than claiming parity from per-call limits.
9. The decisive causal test is private-evidence partition with ownership swaps, ablations, equal-budget single-model union-of-evidence controls, best-of-K and independent verification.
10. A positive synergy statistic must predict held-out external utility after controlling for compute, model strength, communication volume and selection quality.
11. No evidence in this pass establishes universal multi-agent superiority, AGI, consciousness, immortality, full regeneration or a validated Holobiont-wide collective advantage.


## Pass 38 update — 2026-11-23: effective organ independence and common-mode failure

1. Functional complementarity and response diversity are distinct. Complementary organs should add unique capability/evidence; redundant backups for the same function should exhibit different failure responses under matched perturbations.
2. Model count, provider count, prompt diversity, semantic output distance and parameter distance do not establish independent failure behavior.
3. Correctness/error correlation can cap variance-based effective voter count. The equicorrelation formula is N_eff = N/[1+(N-1)rho], but it assumes equal competence and common pairwise correlation and is not a universal count of information or intelligence.
4. Correlation must be measured per task family and perturbation/failure mode. A single global number can conceal clustered or higher-order common-mode failures.
5. Different model families can reduce measured correlation relative to same-model samples/personas, but the November 2026 proof-of-concept still finds only about two effective voters among five cross-provider models; equal-weight plurality remains below the strongest member.
6. Output-derived NCD residuals are a promising preprint-level predictor of correlated wrong-answer agreement beyond semantic distance and capability, but they do not recover internal model mechanisms and the association is not causal.
7. Standard diversity measures can be heavily capability-confounded. Selection claims must be evaluated against the strongest member on held-out items and with capability controls.
8. D-FUSEr provides peer-reviewed evidence that targeted error-distribution shaping can improve tested aggregation/refinement, but this is not evidence that deliberately inducing errors is safe for critical organs.
9. HiddenBench shows that complementary private information can remain unused unless agents actively elicit what others know. Functional complementarity does not automatically become collective utility.
10. Receiver-side Byzantine filtering and robust graph assumptions can preserve information under bounded threat models, but do not guarantee truth when evaluators share blind spots.
11. The organ registry should track model/data lineage, prompts, memory, evaluators, codecs, hypernetworks, tools and infrastructure. Unknown provenance must remain unknown, not be assumed independent.
12. The next decisive step is an organ-independence audit followed by common-mode fault injection and repair tests under shared-dependency compromise.
13. No evidence in this pass establishes a universal effective-organ count, universal ensemble advantage, full Holobiont resilience, complete regeneration, AGI, consciousness or immortality.
