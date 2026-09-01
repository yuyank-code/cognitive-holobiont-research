# Current Conclusions — 2026-09-01

## High-confidence conclusions

1. Modular specialization and conditional computation are mature ideas; modern MoE is a primary baseline against which Holobiont novelty must be tested.
2. Hypernetworks can generate neural weights or parameter-efficient adaptations, and 2026 work shows descriptor-conditioned generators can instantiate heterogeneous architectures in tested regimes; this still does not establish lossless regeneration of arbitrary large specialists.
3. Ensembles and heterogeneous aggregation can improve reliability in bounded settings, but correlated/common-cause errors remain a major limitation.
4. Agreement/consensus is not equivalent to semantic truth; reliability-aware aggregation and Byzantine defenses are more defensible primitives.
5. The shared-versus-independent structure tradeoff is a first-order design constraint.
6. Functional diversity cannot be inferred from parameter diversity alone.
7. Latent communication is now a credible engineering mechanism, but causal evidence for genuinely novel task-relevant information transfer remains unresolved.

## Medium-confidence conclusions

1. Direct latent communication between neural agents is feasible and can improve cooperative performance in some settings.
2. A shared communication interface may be more appropriate than a single shared latent representation: private internal geometries can remain specialized while adapters/translation layers provide interoperability.
3. Hub-and-spoke latent interfaces may improve scalability by reducing pairwise alignment complexity, but information bottleneck and latent-channel security remain unresolved.
4. Hypernetwork-generated specialization and bounded self-modification are increasingly supported, but full specialist regeneration and general recursive self-rearchitecture remain unresolved.
5. Redundancy can reduce failure rates even under correlated failures, but diversity must target causal failure mechanisms rather than model identity alone.

## Important methodological constraints

1. Model stitching success is not sufficient evidence for semantic equivalence or shared cognition. Task-loss stitching can be misleading, and invariance-aware/bidirectional tests are needed.
2. Latent communication performance gains are not sufficient evidence for genuinely novel information transfer. Post-training sender-only information, message-replacement, and receiver-isolation controls are required.
3. Latent-channel probe information is not automatically task-relevant semantic information; negative results must be retained alongside positive results.
4. Organ independence should be measured using correlated failures, activation/behavioral diversity, OOD/adversarial transfer, and calibration correlation—not weight distance alone.
5. Consensus experiments must include correlated, colluding, specification-driven, and useful-minority errors.
6. Regeneration must be evaluated on rare capabilities, robustness, calibration, OOD behavior, and behavior distributions, not benchmark accuracy alone.

## Unresolved

- Whether latent communication can causally transfer genuinely novel task-relevant information unavailable to the receiver.
- Whether private representations plus a shared interface outperform a forced shared latent space at matched communication bandwidth and compute.
- How failure correlation scales with shared weights, training data, memory, routing, specification, and repair generators.
- Whether a learned reliability layer can improve truth under correlated and colluding specialists without suppressing useful minority information.
- The information-theoretic minimum description required to reconstruct a specialist, especially when its unique capability is absent from all surviving modules.
- Whether distributed components can recover unique capabilities more faithfully than any individual surviving component or standard hypernetwork/adapter baseline.
- Whether recursive architecture modification can improve capability while retaining old capabilities over many generations.
- Whether the complete Holobiont lifecycle has a measurable advantage that cannot be decomposed into existing MoE + ensemble + communication + memory + repair components.

## Current strongest Holobiont hypothesis

A potentially useful collective architecture may consist of heterogeneous specialists with private internal representations, a learned interoperable communication protocol, explicit epistemic metadata/provenance, distributed memory/evidence, common-mode-failure detection, capability-level regeneration, and tightly evaluated reconfiguration. This is a hypothesis, not a validated architecture.

## Research posture

No strong claim in the originating treatise should be upgraded to established status merely because its components have demonstrated feasibility. The latest evidence makes the full-system claim more demanding: the Holobiont must demonstrate a measurable capability, information-transfer property, or resilience advantage that simpler MoE, shared-backbone+adapter, ensemble, multi-agent, and repair baselines cannot reproduce at matched resources.
