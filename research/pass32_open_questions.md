# Pass 32 — Open Questions and Falsification Agenda
Date: 2026-10-22

1. Can dependency edges be induced from raw histories with enough precision and recall for cascading invalidation to beat a no-propagation baseline?
2. What is the trade-off between missed invalidation and false invalidation under graph noise?
3. Can a system distinguish a fact's temporal validity from its source integrity and evidential support without collapsing them into a scalar?
4. How should trusted-source compromise, correlated sources, and manufactured corroboration be handled when independence cannot be assumed?
5. Can origin-bound authority be propagated across heterogeneous agents without trusting model-generated lineage?
6. Does preserving historical records improve historical-query utility without reintroducing stale premises into current decisions?
7. Do bitemporal writes and deterministic audit logs remain correct under distributed concurrency, retries, and model/judge-version changes?
8. Does explicit authorization gating reduce consequential memory-poisoning attacks without unacceptable benign false rejection?
9. Can a unified execution/evidence trace be tamper-evident while respecting privacy and minimizing stored sensitive content?
10. Does the combination outperform a simpler stack on held-out long-horizon tasks at matched total cost?

## Falsification conditions

- If oracle-graph benefits vanish with modest realistic graph noise, dependency propagation is not ready for general deployment.
- If false invalidation or benign false rejection offsets reductions in stale/unauthorized actions, simplify the design.
- If origin binding does not outperform lineage-only controls under paraphrase, tool echo, and manufactured corroboration, reject the claimed integrity benefit.
- If bitemporal consistency improves replay but not semantic outcomes, retain it only as a data-integrity layer and do not claim reasoning gains.
- If the combined system cannot beat simpler temporal retrieval plus explicit action authorization at matched cost, do not retain the full combined architecture.
- Any hard authorization or privacy violation must be reported separately; it cannot be compensated by higher mean task accuracy.
