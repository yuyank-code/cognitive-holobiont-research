# Falsification Framework

The program prioritizes experiments that could make the Holobiont hypothesis fail. The treatise is not evidence.

## Run 19 additions

### F19.1 — Longitudinal specialist-identity test
Train modular systems jointly for many phases after inducing specialization. Compare standard MoE, Path-Constrained routing, EMO-style modularity, and independently trained specialists. Measure retention of causal task capability, routing stability, representational drift, cross-specialist interference, and post-damage recovery.

**Falsifies strong organ-identity claim if:** specialization repeatedly disappears under continued training or if simpler routing mechanisms reproduce the same retention.

### F19.2 — Strict latent-information causal audit
For each latent relay, test: matched sender/example, mismatched sender/example, zeroed message, moment-matched random message, and receiver-private-information vs non-private-information regimes. Repeat across architectures/projectors.

**Falsifies universal latent-thought claim if:** sender/example pairing effects disappear under replication or occur only when the receiver already has equivalent information.

### F19.3 — Communication phase diagram
Sweep group size, graph density, bandwidth, message frequency, and specialist correlation. Measure task utility, K_eff, capability diversity, epistemic diversity, representation coupling, joint failure probability, and coordination overhead.

**Falsifies communication-control hypothesis if:** no reproducible regime exists in which communication raises useful collective capability without proportional coupling/failure cost.

### F19.4 — Consensus vs dependency-aware dissent
Create tasks with independent correct evidence, correlated false evidence, colluding specialists, specification errors, and useful minority specialists. Compare majority vote, confidence weighting, Byzantine weighting, provenance-aware fusion, Free-MAD-like trajectory scoring, and abstention.

**Falsifies truth-oriented fusion hypothesis if:** dependency-aware methods do not outperform simple consensus or systematically suppress useful minorities.

### F19.5 — Distributed capability-regeneration benchmark
Encode a rare capability at controlled redundancy levels across specialists and a generator. Destroy specialists at test time. Compare exact regeneration, behavior-level recovery, OOD robustness, calibration, conflict fidelity, and collateral regressions against standard hypernetwork/LoRA and independent-copy baselines.

**Falsifies strong regeneration claim if:** recovery requires an intact copy of the capability or is no better than standard redundancy/generation under matched information budgets.

### F19.6 — Recursive meta-evolution retention
Allow validated changes to routing, memory, topology, and repair policies over many generations. Require improvement on new tasks plus non-regression on a frozen historical suite and adversarial tests.

**Falsifies bounded recursive-rearchitecture claim if:** gains are transient, evaluator-specific, or accompanied by irreversible capability loss.

## Existing decisive experiments

- Compute-matched single-model multi-output/self-conditioning baseline.
- MoE vs heterogeneous independent specialists vs shared-backbone+adapters.
- Text communication vs latent communication at matched transmitted information.
- Randomized topology and communication ablations.
- Common-mode failure injection: shared data, shared backbone, shared memory, shared router, shared evaluator, shared generator.
- Specialist deletion followed by repair/regeneration.
- Correlated Byzantine/collusion attacks.

## Evaluation principle

A positive result is only meaningful if it survives matched compute, memory, bandwidth, information, training-data, and redundancy budgets. Full-system novelty requires an advantage that cannot be decomposed into an existing component's known benefit.
