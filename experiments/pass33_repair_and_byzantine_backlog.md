# Experiment Backlog — Pass 33: Regeneration and Immune Reliability

## E33-A — Organ regeneration under controlled information removal

**Question:** Can surviving organs recreate a missing specialist's capability without access to a hidden backup or target-specific teacher?

### Setup
- Train two heterogeneous specialist models with overlapping and unique task subsets.
- Train a shared generator/repair mechanism under an explicitly recorded information budget.
- Freeze and evaluate both specialists on a held-out capability suite before deletion.
- Delete one specialist and remove target-specific checkpoint, adapters, optimizer state and direct teacher activations.
- Attempt recovery using only declared surviving artifacts.

### Ablation ladder
1. Checkpoint retained (positive control).
2. Checkpoint removed, adapters retained.
3. Checkpoint and adapters removed, target training examples retained.
4. Target examples removed, compressed memory and logs retained.
5. Only surviving specialist states, shared generator and general task descriptors retained.
6. Shared generator/codec corrupted.
7. One or more surviving organs removed or poisoned.

### Baselines
- Exact checkpoint restore.
- Distilled backup.
- Fresh retraining from the same permitted data.
- Nearest available specialist.
- HyperRepair-style generated side-net.
- UHN-style descriptor-conditioned generation.
- Random initialization and no-recovery fallback.

### Measurements
- Held-out functional utility and capability breadth.
- Exact-weight recovery only where meaningful.
- Calibration and uncertainty.
- Robustness and safety regressions.
- Recovery latency, compute, memory and bandwidth.
- False recovery: candidate appears healthy on repair data but fails held-out tests.
- Common-mode failure rate.

### Falsification
If recovery collapses when target-specific information is truly removed, the result supports backup/teacher-assisted repair, not distributed regeneration.

## E33-B — Repair with and without a pristine teacher

Replicate a small SHNN-style localized repair task. Compare clean teacher activations, replay data, peer-generated targets, shared hypernetwork, and no target-specific reference. Measure collateral capability loss and false repair of healthy layers.

## E33-C — Multi-objective immune repair

Use an NSRepair-like repair objective with two simultaneous defects (e.g., backdoor plus robustness, or safety plus fairness). Compare single-objective sequential repair, joint Pareto repair, and no repair. Measure whether fixing one defect worsens the other or erases valid specialist behavior.

## E33-D — Byzantine containment under common-mode failure

Use SAC as a baseline. Add shared retrieval poisoning, model-family correlation, evaluator compromise, correct minority evidence, adaptive per-recipient messages, and dynamic graph churn. Compare majority vote, sender confidence, receiver-side scoring, trusted verifier, provenance-aware admission and hybrid filters.

Measure accuracy, false acceptance, false rejection, calibration, recovery time, token/compute cost, bandwidth and availability.

## E33-E — Recoverable self-modification

Change a bounded route, bridge version or memory schema. Inject concurrent updates, partial writes, crashes and changed dependencies. Compare full snapshots, effect-scoped snapshots, write-ahead logging, synthesized inverses and EvoUndo-style verified recovery.

A mutation is admitted only if it improves held-out utility and restores an observationally equivalent pre-state across counterfactual conditions. Use snapshots/WAL when exact state is known; use synthesized recovery only when inverse semantics are not directly available.

## E33-F — Fair resource accounting

For all E33 experiments, match or explicitly report training compute, inference compute, memory, bandwidth, latency, information access and verifier budget. Include the cost of routing, retries, repair training and independent evaluation. Report Pareto frontiers; do not hide trade-offs in a single score.
