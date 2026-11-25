# Architecture Note — Pass 40
## Recovery Tiers and Peer-Assisted Reconstruction Protocol
**Date:** 2026-11-25

## Design objective

Preserve the Treatise's ambition that surviving organs can help restore a failed organ, while preventing ordinary rollback, checkpoint repair, skill retrieval or teacher distillation from being mislabeled as regeneration.

## Recovery tiers

### Tier 0 — Continuity and rollback
Replicas, checkpoints, versioned manifests and hot/warm standbys. This is essential reliability engineering, but it restores saved state rather than regenerating it.

### Tier 1 — Local fault correction
A surviving model receives a bounded patch, residual controller or localized repair. The original base remains intact. Use when damage is focal and the diagnostic signal is trustworthy.

### Tier 2 — Checkpoint-conditioned restoration
A repair generator uses a surviving base/fine-tuned pair, activation fingerprint or task-vector delta. HyperRepair and DG-Hard are examples of this class. Record the required lineage and reference artifacts.

### Tier 3 — Procedural adaptation
A verified failure produces a reusable skill, textual lesson or small adapter. Self-Direction is an example. Keep the base frozen, route conservatively and retain a clean-base fallback.

### Tier 4 — Behavioral reconstruction from surviving information
The original target is unavailable to the recovery system. Surviving organs provide permitted examples, evidence, traces or outputs from which a new specialist is trained or distilled. This is the first tier that directly tests the distinctive peer-regeneration claim.

### Tier 5 — Exact parameter reconstruction
Reproduce the original parameter tensor. Treat as a separate and much stronger objective. Do not require it when behavioral recovery is the actual goal, and do not claim it without parameter-level evidence.

## Recovery manifest

Every organ should have a signed, versioned capability and dependency manifest:
- capability slices and known limitations;
- model/checkpoint/adapter hashes;
- base model and training lineage;
- data and supervision sources;
- memory, trace and tool dependencies;
- hypernetwork and codec versions;
- evaluator and safety-test versions;
- permitted recovery information;
- recovery tier and rollback target.

Unknown fields must remain unknown, not be inferred as independent or absent.

## Recovery lifecycle

1. Detect failure and classify it: corruption, drift, forgetting, infrastructure loss or deletion.
2. Quarantine the failed organ and freeze its current state for forensic evaluation.
3. Declare the deletion boundary and surviving-information manifest.
4. Select the least powerful recovery tier that matches the failure.
5. Generate the repair or replacement in a sandbox.
6. Evaluate against the offline capability manifest, including rare, OOD, adversarial and safety slices.
7. Compare with the strongest fallback and matched resource budget.
8. Canary the replacement with restricted permissions.
9. Reintegrate only after independent validation; preserve rollback and provenance.
10. Record which retained sources caused recovery gains.

## Hypernetwork DNA governance

- Do not make one hypernetwork the sole recovery path for all organs.
- Separate repair generation from repair approval.
- Use independent evaluators and source provenance.
- Keep repair-training data and generated adapters versioned.
- Test repair-generator corruption and common-mode failure.
- Preserve a stable base or rollback path where possible.
- Monitor long-term plasticity and capability interference after repeated repair.

## First implementation boundary

The first experiment should use two or three small, genuinely different specialists and a single bounded capability with a hidden evaluation split. Do not start with an unrestricted self-modifying organism. First prove that peer-retained information adds recovery value beyond backup, retrieval, generic self-generation and ordinary distillation.
