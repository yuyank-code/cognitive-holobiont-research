# Architecture Note — Pass 42: Contract-Driven Graceful Degradation

## Purpose

Translate the Treatise's continuity and resilience goals into explicit, testable service behavior under partial failure.

## Operating modes

- M0 Full federation: all required organs, channels and verifiers available.
- M1 Communication-degraded: disable latent channels; retain typed provenance-bearing messages.
- M2 Specialist-degraded: remove unavailable optional organs only when remaining evidence/capability contracts still hold.
- M3 Read-only: continue analysis but fence external side effects.
- M4 Safe pause/abstain: no admissible completion path remains or control-plane trust is lost.

A mode selector maximizes useful task value subject to hard safety, authorization, provenance and budget constraints. It cannot relax those constraints to preserve availability.

## Contract stack

1. Task contract: outcome, minimum quality, deadline, evidence, partial-result semantics.
2. Organ contract: capability scope, version, dependencies, schemas, health and fallback behavior.
3. Action contract: identity, authority, data scope, preconditions, postconditions, idempotency, budget and audit.
4. Delegation contract: stricter profile, permission intersection, approval accumulation and atomic budget reservation.
5. Recovery contract: replayability, rollback point, irreversible effects and independent validation.
6. Service contract: safe completion, useful degraded completion, latency, false intervention, unsafe effects and audit completeness.

## Runtime components

- Heart: selects workflow/mode and coordinates, but is not sole safety authority.
- Local effect gateway: enforces permissions and postconditions even if Heart is unavailable.
- Amygdala: requests stricter modes and evaluates risk; cannot mint provenance or widen authority.
- Hippocampus: stores versioned traces and evidence ancestry; supports rollback/replay and taint closure.
- Connective tissue: returns typed fallback states when a channel or organ is unavailable; must not invent missing evidence.
- Meta-Organ: may propose topology/mode policy changes through sandboxed review, not modify policy roots or enforcement code.

## Resilience patterns

- Circuit breaker per organ/tool to stop repeated failing calls.
- Typed fallback result with explicit missing capability/evidence.
- Cross-component quality gates for semantic consistency.
- Verify-before-retry for non-atomic side effects.
- Idempotency key plus postcondition check where supported.
- Append-only trace with action, authority, version and evidence lineage.
- Local enforcement and safe mode during coordinator outage.
- Human escalation for actions whose consequence exceeds the autonomous envelope.

## Key design constraint

Availability must not be achieved by silently lowering safety or evidence requirements. If no mode can meet the task contract, the system should abstain or pause and state which capability is missing.
