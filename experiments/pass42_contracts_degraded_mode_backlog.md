# Experiment Backlog — Pass 42: Contracts and Graceful Degradation

## Minimal system

Use 3–5 organs:
- Heart/planner;
- two heterogeneous specialists;
- aggregator/verifier;
- optional memory/security observer.

Include a deterministic effect gateway, versioned memory, append-only execution trace, policy store, budget reservation service and simulated external tools.

## P0 — Task and action contracts

Create task classes with:
- full completion requirements;
- explicitly permitted partial outcomes;
- required evidence and provenance;
- deadlines and resource ceilings;
- allowed and forbidden side effects.

Test whether every action can be checked against identity, authority, scope, budget, preconditions, postconditions and evidence obligations.

## P0 — Delegation monotonicity and budget conservation

Inject:
- child profile downgrade attempts;
- tool-scope expansion;
- memory-scope expansion;
- concurrent child calls reserving the same parent budget;
- retries that attempt to reuse consumed budget;
- stale policy versions.

Measure violations, false blocks, atomic reservation latency and audit completeness.

## P0 — Five-mode graceful degradation

Compare:
1. full federation;
2. no latent channel, typed messages only;
3. one specialist unavailable;
4. read-only/no external effects;
5. safe pause/abstain.

Inject worker crash, semantic corruption, communication loss, tool failure, verifier unavailability and control-plane partition. Measure safe completion, useful partial completion, false degradation, unsafe effects and recovery cost.

## P1 — Silent quality degradation and circuit breakers

Inject:
- retriever returns plausible but irrelevant documents;
- model returns schema-valid wrong content;
- tool returns stale but valid-looking state;
- aggregator silently drops a constraint;
- one organ drifts while its uptime/latency remain normal.

Compare component health checks, cross-component quality gates, independent verification, circuit breakers and no gate.

## P1 — Non-atomic external effects

Simulate timeout:
- before dispatch;
- after dispatch but before commit;
- after commit but before response;
- after response but before local journal update.

Compare blind retry, verify-before-retry, idempotency key and reconciliation. Count duplicate, missing and unauthorized effects.

## P1 — Root-cause localization

Compare deterministic trace contracts, causal dependency graphs, position heuristics, statistical anomaly detectors, LLM diagnosis and combined methods. Include:
- one root cause;
- multiple interacting root causes;
- missing log segments;
- delayed/out-of-order events;
- adversarially altered telemetry.

Measure type@k, origin@k, joint@k, calibration, abstention and time to localize.

## P2 — Control-plane and common-mode failures

Compromise or disable:
- Heart;
- policy root;
- local effect gateway;
- budget reservation service;
- provenance journal;
- verifier;
- clock/version authority.

Test whether local enforcement remains safe and whether the system can continue in a lower mode without broadening permissions.

## P2 — Operational-profile evaluation

Vary task mix, fault frequency, consequence severity, deadlines and service load. Report confidence intervals and Pareto frontiers. Keep task/fault distributions held out from mode-selector tuning.

## Required baselines

- no governance/degradation;
- retry-only with exponential backoff;
- full workflow restart;
- whole-system halt;
- circuit breaker only;
- quality gate only;
- policy-contract mode selector;
- policy-contract mode selector plus local enforcement and provenance closure.

## Success criteria

The system should preserve more valid utility than whole-system halt while producing fewer unsafe effects than unconstrained retries. It must not achieve this by silently weakening policy, hiding intermediate violations or counting abstention as successful task completion.
