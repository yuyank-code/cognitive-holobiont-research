# Contradictions and Open Problems — Pass 40
**Date:** 2026-11-25  
**Topic:** Capability recoverability and regeneration.

## Contradictions and tensions

1. **“No target data at deployment” vs. no information dependency.** HyperRepair does not use target-domain examples or optimize the target at deployment, but it is trained using source repairs and labeled general examples, and it still receives a surviving target model's activation fingerprint.
2. **Repair vs. regeneration.** HyperRepair and DG-Hard repair a surviving fine-tuned model. Neither recreates a missing specialist after all target artifacts are removed.
3. **Persistent lesson vs. new organ.** Self-Direction creates a procedural adapter for a base model. This can improve recurring workflows but does not rebuild a specialist's full domain distribution, calibration, multimodal capability or internal representation.
4. **Merging vs. resurrection.** PRISM can reduce destructive interference when combining available specialist checkpoints. It cannot recover a specialist that is not among the inputs.
5. **Behavioral copying vs. information-free recovery.** Distillation can copy behavior while a teacher or sufficiently informative traces remain accessible. This is a transfer channel, not evidence of spontaneous recovery after deletion.
6. **Average recovery vs. rare capability retention.** Aggregate scores can hide loss of rare, safety-critical or OOD behavior. A regenerated organ must be tested on a capability manifest, not a single mean score.
7. **Local correction vs. global competence.** Residual patches can correct bounded faults while leaving the original model frozen. This is safer than global updates in some settings but does not imply broad domain repair.
8. **Plasticity vs. specialization stability.** Repeated adaptation can make a component less able to learn future tasks. A repair process that restores today's score but destroys tomorrow's adaptability is not successful regeneration.
9. **Shared DNA vs. common-mode failure.** A single hypernetwork, repair dataset, codec or evaluator can become a system-wide dependency. Distributed organs do not automatically imply distributed recovery authority or knowledge.
10. **Exact weights vs. functional equivalence.** Reproducing parameters is a much stronger target than reproducing behavior on a declared task distribution. The project should not conflate them.

## Open questions

- What fraction of a lost organ's capability is encoded in surviving peers' weights, memories, adapters, traces and shared training history?
- Can that retained information be measured before the repair attempt?
- How does recovery change when the original base checkpoint is removed but the peer organs retain overlapping pretraining?
- Can one organ reconstruct another from examples of its decisions without reproducing its errors and blind spots?
- How many diverse, independently sourced examples are required to recover rare capabilities and calibration?
- Does peer-assisted distillation generalize to held-out domains and modalities, or only interpolate within observed task families?
- Can a hypernetwork trained on one model family generate repairs for genuinely heterogeneous architectures?
- Does repeated repair cause the hypernetwork to overfit to its own prior outputs or collapse specialist diversity?
- Can a recovery process remain trustworthy when the verifier, memory lineage or repair generator is partially compromised?
- What is the minimum surviving information required for behavioral equivalence at a chosen tolerance?

## Negative-result requirements

The benchmark must include:
- no-information and wrong-information controls;
- a generalist fallback;
- an ordinary checkpoint restore;
- adapter/retrieval memory;
- model merging;
- teacher distillation with declared query budgets;
- full retraining on exactly the surviving data;
- deliberate removal of the repair hypernetwork or its training examples;
- tests for rare, OOD, adversarial and safety behavior.

A failed recovery is informative. It should not be hidden by silently restoring a checkpoint, querying an undeclared teacher, or reintroducing deleted training data.
