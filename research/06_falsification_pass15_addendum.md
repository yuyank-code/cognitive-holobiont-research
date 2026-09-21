# Falsification Framework — Pass 15 Addendum

## Test F15-1: Interaction-tax curve

Construct tasks with deliberately complementary private information. Compare independent solving, passive broadcast, full-solution interaction, selective disagreement retention, and active information requests under equal model-call, token, and bandwidth budgets.

**Falsifier:** if unrestricted/full-solution interaction consistently matches or beats selective protocols without sacrificing independent-solution coverage, the interaction-tax premise is weakened.

## Test F15-2: Governance-constrained information value

For every candidate message/request, estimate expected task gain and impose explicit penalties for bandwidth, convergence, provenance violations, authority violations, and correlated-failure exposure.

**Falsifier:** if an unconstrained information maximizer is consistently as safe and effective as the governed scheduler across adversarial channel conditions, the added governance layer may be unnecessary.

## Test F15-3: Coalition stability vs information diversity

Sweep topology from independent agents to stable coalitions to dense global coupling. Measure task success, unique conditional contribution, failure correlation, and time-to-convergence.

**Falsifier:** if more stable/dense coalitions monotonically improve unique information contribution without increasing correlated failure, the independence/stability trade-off is weakened.

## Test F15-4: Hidden-channel audit

Use private/latent channels while exposing channel metadata, provenance, sender identity, and action traces to an external auditor. Inject collusive or constraint-drifting agents.

**Falsifier:** if hidden channels remain harmless without provenance/audit controls under these adversarial conditions, the current governance concern is overstated.

## Required baseline discipline

All tests must match, as closely as practical:
- total inference compute;
- parameter/quality budget;
- communication bandwidth;
- memory/token budget;
- number of independent samples;
- verifier calls;
- external information access.

Success must be reported with confidence intervals and failure-correlation statistics, not only mean task accuracy.
