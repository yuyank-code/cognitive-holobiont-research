# Living Literature Map — Pass 40
**Date:** 2026-11-25  
**Theme:** What can be repaired, restored, copied or regenerated after specialist capability loss?

## Cluster A — Hypernetwork-generated repair of surviving models
- HyperRepair, arXiv:2610.41147: activation fingerprint conditions a hypernetwork that generates a gated repair side-net for a surviving fine-tuned model.
- Prior HyperNetworks literature establishes parameter generation as a mechanism, not arbitrary information recovery.

**Synthesis:** Bounded post-hoc restoration is promising. The target checkpoint, backbone lineage and trained repair generator remain available. This does not establish regeneration after target deletion.

## Cluster B — Persistent procedural repair
- Self-Direction, arXiv:2610.31846: failure traces become small LoRA adapters in a persistent, routed library.
- Reflexion and skill-memory methods are neighboring baselines; textual skill storage is competitive in some reported comparisons.

**Synthesis:** A system can learn reusable procedures from verified failures without rewriting its base model. This is narrower than restoring a specialist's full capability distribution.

## Cluster C — Checkpoint-conditioned forgetting repair
- Spectral Unforgetting, arXiv:2605.20296: uses the base/fine-tuned weight delta to remove a spectral residual.
- HyperRepair uses a surviving fine-tuned model plus an activation fingerprint and a pretrained repair hypernetwork.

**Synthesis:** Repair can be data-light at deployment, but information is retained in checkpoints and training lineage. Declare these dependencies.

## Cluster D — Model merging and specialist integration
- PRISM, arXiv:2610.03199: screens and repairs destructive merging of available shared-base specialist task vectors.
- TIES, DARE, DELLA and task arithmetic are important comparison methods.

**Synthesis:** Merging is a candidate integration route, not regeneration. It can itself destroy capability through interference.

## Cluster E — Behavioral distillation and model extraction
- Identified-Set Geometry, arXiv:2605.10407: quantifies top-K distribution ambiguity and separates logit fidelity from capability transfer; generation access provides a stronger transfer channel in same-family experiments.
- On-policy distillation and generated-trajectory training are relevant neighboring mechanisms.

**Synthesis:** A capability can be copied when the teacher remains queryable and enough informative trajectories are available. This is not information-free resurrection.

## Cluster F — Plasticity and local fault correction
- Spectral Collapse Drives Loss of Plasticity, ICML 2026: repeated continual learning can degrade future learnability.
- Cerebellar-Inspired Residual Control, ICML 2026: local residual correction can recover bounded robotic policies while the base remains frozen.

**Synthesis:** Preserve plasticity and prefer bounded correction routes where possible. Neither paper establishes language-model organ regeneration.

## Missing evidence

No source in this pass demonstrates a heterogeneous federation removing a specialist's weights, unique data, adapters and teacher access, then recovering its held-out capability from surviving peers alone. This remains the core open empirical gap for Hypernetwork DNA.
