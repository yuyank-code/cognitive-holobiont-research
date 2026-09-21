# Architecture Pass 15 — Governed Epistemic Scheduler

## Revised architecture

private heterogeneous specialists
→ capability-aware routing
→ local hypothesis generation
→ epistemic-state estimation
→ governed information scheduler
→ selective communication / information request
→ provenance + constraint propagation
→ dependency-aware integration
→ independent verification
→ task-anchor + termination controller
→ distributed memory / capability traces
→ bounded repair
→ validation-gated reconfiguration

## New scheduler responsibilities

The scheduler must decide among at least six actions:

1. **Ask** — request a specific missing fact/capability.
2. **Share** — transmit information whose conditional value exceeds its coupling/governance cost.
3. **Preserve** — withhold information temporarily to maintain independent search.
4. **Challenge** — request an independent derivation or disagreement-preserving alternative.
5. **Quarantine** — isolate a source/channel when provenance, safety, or collusion risk is high.
6. **Terminate** — stop interaction when marginal expected value is below total cost.

## Architectural principle

The system should not maximize consensus. It should maximize reliable task progress while preserving enough epistemic independence to detect error and avoid correlated failure.

## Why this is not yet validated

Every element above has partial precedent in existing work, but there is no evidence yet that the integrated scheduler produces positive coalition synergy on exact distributed-computation tasks under matched resources. The architecture remains a research hypothesis.
