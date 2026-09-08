# Falsification Framework

The program prioritizes experiments that could make the Holobiont hypothesis fail. The treatise is not evidence.

## Run 20 additions

### F20.1 — Receiver-isolated latent information bound
Construct tasks where a unique fact exists only in the sender's private input. Compare matched sender/example, mismatched sender/example, zeroed, and moment-matched random latent payloads. Measure receiver uncertainty reduction and final-task benefit.

**Falsifies strong latent-transfer claim if:** matched sender-specific payloads do not produce reproducible information gain when the receiver lacks the information elsewhere.

### F20.2 — Distributed integration bottleneck test
Give identical distributed facts to (a) a single model with a larger context, (b) independent agents with text communication, (c) latent communication, and (d) a structured shared-state coordinator. Match total tokens/compute. Separately measure acquisition and integration errors.

**Falsifies Holobiont distributed-computation advantage if:** the architecture never beats the single-model or simpler structured-state baseline on integration after matching resources.

### F20.3 — Topology-aware uncertainty calibration
Run identical tasks over multiple communication graphs and repeated stochastic executions. Compare output-only confidence against trajectory/topology-aware uncertainty. Inject correlated failures and common evidence.

**Falsifies topology-aware reliability hypothesis if:** topology/trajectory features do not improve calibration or selective prediction over output-only confidence.

### F20.4 — Interface portability matrix
Evaluate training-free and learned latent bridges across model families, scales, modalities, and stitch depths. Measure transfer, degradation, adaptation cost, and cross-task generalization.

**Falsifies portable-interface hypothesis if:** successful interoperability requires substantial task/model-specific retraining in most heterogeneous pairs.

### F20.5 — Honest-correlated-error Byzantine test
Create groups where honest specialists share a systematically wrong source, while a minority specialist holds correct evidence. Compare majority, confidence weighting, Byzantine filtering, provenance-aware fusion, and abstention.

**Falsifies truth-oriented immune-system claim if:** dependency-aware methods cannot preserve correct minorities or distinguish correlated honest error from independent evidence.

## Existing decisive experiments retained

- Longitudinal specialist-identity test.
- Strict latent-information causal audit.
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
