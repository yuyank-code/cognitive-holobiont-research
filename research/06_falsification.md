# Falsification Framework

The program prioritizes experiments that could make the Holobiont hypothesis fail. The treatise is not evidence.

## Run 22 additions

### F22.1 — Selector bottleneck decomposition
Generate candidate solutions using homogeneous and heterogeneous specialists, then cross the candidates with independent selectors of varying quality. Match total compute. Measure where diversity helps, hurts, or becomes irrelevant.

**Falsifies a strong diversity claim if:** after controlling selector quality, heterogeneous candidates provide no advantage over matched homogeneous/self-conditioned candidates.

### F22.2 — Effective-channel causal validation
Estimate K* or related effective-channel measures, then deliberately introduce correlated failures, shared evidence, model cloning, and independent model substitutions. Test whether the metric predicts marginal utility and failure diversity out of sample.

**Falsifies K* as a useful abstraction if:** it does not predict collective gains or correlated failure under interventions better than raw agent count/simple correlation baselines.

### F22.3 — Distributed-state integration benchmark
Use tasks where each specialist receives indispensable private facts. Compare single-model large-context, text-MAS, latent-MAS, structured shared-state, and Holobiont-style interfaces under matched total information and compute. Separately score acquisition, integration, and termination.

**Falsifies distributed-computation advantage if:** the Holobiont never beats the simplest matched integration baseline on exact tasks.

### F22.4 — Long-horizon topology stability test
Run open-ended coordination while adaptively rewiring the graph. Measure whether topology changes preserve capability, calibration, and diversity rather than producing hub dominance, drift, or communication explosion.

**Falsifies safe adaptive-topology hypothesis if:** utility gains consistently require unstable topology, uncontrolled coupling, or worse correlated-failure rates.

### F22.5 — Specialist causal identity test
After creating specialists, continue shared training, perturb routing, ablate suspected causal circuits, and substitute parameters. Track capability-specific interventions over time.

**Falsifies organ identity hypothesis if:** specialization is explained by transient routing/geometry and disappears under mild continuation or intervention.

### F22.6 — Selection versus synthesis replication
Replicate selection-bottleneck results using independent selectors, ground-truth tasks, and non-LLM judges. Compare generate-then-select, debate, synthesis, majority vote, and dependency-aware fusion.

**Falsifies selection-bottleneck claim if:** the crossover disappears under independent evaluation or does not replicate outside judge-dependent settings.

## Existing decisive experiments retained
- Receiver-isolated latent information bound.
- Distributed integration bottleneck test.
- Topology-aware uncertainty calibration.
- Interface portability matrix.
- Honest-correlated-error Byzantine test.
- Longitudinal specialist-identity test.
- Communication phase diagram.
- Consensus vs dependency-aware dissent.
- Distributed capability-regeneration benchmark.
- Recursive meta-evolution retention.
- Compute-matched single-model multi-output/self-conditioning baseline.
- MoE vs heterogeneous independent specialists vs shared-backbone+adapters.
- Text communication vs latent communication at matched transmitted information.
- Randomized topology and communication ablations.
- Common-mode failure injection: shared data, shared backbone, shared memory, shared router, shared evaluator, shared generator.
- Specialist deletion followed by repair/regeneration.
- Correlated Byzantine/collusion attacks.

## Evaluation principle

A positive result is only meaningful if it survives matched compute, memory, bandwidth, information, training-data, and redundancy budgets. Full-system novelty requires an advantage that cannot be decomposed into an existing component's known benefit.
