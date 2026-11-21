# Architecture Note — Pass 36: Governed Meta-Organ

## Purpose

The Meta-Organ is the subsystem that proposes and coordinates changes to the Cognitive Holobiont's specialist population, roles, communication graph, memory policies and resource allocation. It is not an unrestricted root process.

## Separation of duties

1. **Observer:** records outcomes, traces, resource use, faults and safety events.
2. **Diagnostician:** proposes a causal explanation for a capability or coordination failure.
3. **Mutation proposer:** emits a typed, versioned delta against an allowed schema.
4. **Deterministic validator:** checks graph invariants, references, budgets, permissions and allowed operations.
5. **Sandbox evaluator:** replays tasks and protected suites without production privileges.
6. **Independent evaluator/approver:** verifies utility and safety using separate evidence or model/control dependencies.
7. **Canary manager:** limits rollout and watches for regressions.
8. **Rollback manager:** restores validated state or executes compensating procedures.
9. **Immutable registry/audit:** records proposals, approvals, exact versions, test results and lineage.

## Initial mutation permissions

Start with the least risky class:
- add/remove a communication edge;
- adjust information visibility within existing permissions;
- choose among pre-registered agent roles;
- activate/deactivate an existing specialist within a fixed budget;
- add a verifier from a pre-approved registry.

Do not initially allow:
- arbitrary code execution or new tool privileges;
- direct weight changes;
- mutation of the evaluator or benchmark;
- changes to authorization roots or safety constitution;
- deletion of rollback records;
- automatic external side effects.

## Mutation lifecycle

Observe → diagnose → propose → schema/permission validate → sandbox → independently evaluate → approve → canary → commit or rollback.

Every mutation must include:
- parent configuration/version;
- target and operation list;
- rationale and evidence;
- expected utility/cost delta;
- permission scope;
- dependency and compatibility impact;
- safety/privacy test results;
- rollback artifact;
- expiration or review condition.

## Key invariants

- No proposal can grant itself new privileges.
- No proposal can alter the evaluator that approves it.
- No single organ can authorize a high-impact mutation it proposed.
- Production changes are atomic at the configuration layer.
- The prior validated configuration remains addressable.
- External side effects require idempotency or compensating actions.
- A failed audit causes fallback to the last validated configuration, not recursive uncontrolled mutation.
- Structural adaptation and model capability learning are recorded as different event types.

## First testable architecture

Three heterogeneous specialist organs (for example, one code/tool specialist, one domain-reasoning specialist and one independent verifier) operate under a fixed agent budget. A separate Meta-Organ proposes only graph/role changes. Deterministic code validates the graph. A sandbox tests changes against paired task prefixes and hidden regression suites. An independent approval process controls canary promotion.

The first experiment should use verifiable coding/tool tasks, then extend to less-verifiable domains only after mutation attribution and safety checks are reliable.

## Why this is not yet the full Holobiont

The architecture does not create new specialist weights, regenerate deleted capabilities or establish organism-like identity. It is a minimal test of safe structural adaptation. It provides a controlled foundation for testing whether more ambitious evolution is justified.
