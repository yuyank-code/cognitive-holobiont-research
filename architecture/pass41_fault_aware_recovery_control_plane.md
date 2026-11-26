# Architecture Note — Pass 41: Fault-Aware Recovery Control Plane

## Purpose

Translate the Treatise's immune system, Heart, Hippocampus, Amygdala and self-healing organs into a testable runtime architecture that detects faults, limits their blast radius, repairs affected state and safely restores service.

## Two planes, explicit boundaries

### Data plane
- Independent specialist organs and their local state.
- Typed messages and latent payloads with versioned metadata.
- Tool calls, memory writes and external effects.
- Task dependency graph and immutable execution identifiers.

### Control plane
- Telemetry collection and trace journal.
- Fault detectors and alert calibration.
- Provenance/taint graph.
- Authorization and per-effect fencing.
- Quarantine and minimum-cut controller.
- Rollback, replay, substitution and repair planner.
- Independent verifier and re-entry gate.

## Core protocol

1. Every invocation receives a unique ID, parent ID, task/session ID, model/version, state version and bounded authority grant.
2. Every message or derived memory records its parent artifacts and permissions.
3. Every external effect is mediated by a local gateway; no organ directly bypasses the gateway.
4. Telemetry records input/output hashes, schema, tool result, timing, retries, state versions and effect status. Sensitive payloads are stored under scoped access, not broadcast to all organs.
5. An alert may originate from deterministic invariant failure, infrastructure signal, independent verifier or model-assisted diagnosis.
6. The controller marks a candidate origin and computes downstream taint closure.
7. Local gateways fence pending affected effects before asynchronous cleanup.
8. Healthy branches continue if their data lineage and permissions are unaffected.
9. The recovery planner chooses recomputation, rollback/replay, substitution or model repair under an explicit budget.
10. A verifier checks task outcome, state consistency, memory descendants, authorization and regression tests.
11. Only validated state is committed and the repaired organ is reintroduced with least privilege.

## Trust and authority

- The Heart coordinates but cannot unilaterally certify truth.
- The Amygdala may request quarantine but cannot mint provenance or override deterministic permission checks.
- Local site guardians can enforce a fail-closed policy during coordinator outage.
- The provenance journal should be append-only and replicated; consistency/availability behavior under partition must be specified.
- The verifier must be independent of the repair proposer where practical.
- A cryptographically authenticated output proves origin/integrity in transit, not semantic truth at the source.

## Failure modes to test

- faulty worker output;
- aggregator logic failure;
- Heart/coordinator crash or compromise;
- provenance journal lag or corruption;
- authorization-root compromise;
- local gateway outage;
- silent wrong tool result;
- stale memory version;
- duplicate/replayed event;
- network partition;
- false alert and alert storm;
- compromised verifier;
- repair that improves one task but regresses another.

## Design decision

The first testable Holobiont resilience prototype should be a small workflow with 3–5 organs, local effect gateways, an append-only dependency journal, deterministic checks and an external recovery controller. It should not begin with autonomous model-weight modification. The first claim to validate is selective containment plus verified state recovery under controlled faults.
