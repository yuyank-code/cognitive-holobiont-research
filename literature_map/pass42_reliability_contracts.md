# Living Literature Map — Pass 42: Reliability Contracts and Graceful Degradation

## Theme

The Holobiont's continuity objective should be evaluated as safe, useful service under partial failure. This theme connects agent trace safety, policy composition, fault injection, root-cause diagnosis, circuit breakers, semantic quality gates and non-atomic tool semantics.

## Evidence map

### Execution-path assurance
- TraceProbe (EMNLP 2026): executable traces expose unsafe intermediate actions hidden by endpoint-only evaluation.
- Trace-Based Assurance Framework (preprint): step/trace contracts, deterministic replay and bounded counterexample search.
- Policy Algebra (preprint): reliable capability as a path property with compositional policy obligations.

### Fault injection and topology
- MAS-FIRE (preprint): 15 fault types; closed-loop workflows mitigate some faults that collapse linear pipelines.
- AgentTrace (preprint): dependency graph and backward root-cause ranking; synthetic single-root assumptions.
- Compound AI System Reliability (preprint): incident taxonomy and resilience patterns at component boundaries.

### Operational governance
- OpsAgent (IEEE ICAISET 2026): observation/reasoning/execution/governance with simulated fault-injection results; abstract-only review here.
- Policy Algebra (preprint): profile/authority narrowing, budget conservation, approvals and evidence obligations.

### External effects
- Verified Tool Calls (preprint): postcondition verification before retry and idempotency keys under non-atomic failures.

## Synthesis

The strongest design principle is that reliability must be attached to the complete path of actions and evidence. The Holobiont should declare a degradation ladder and choose the most capable mode that still satisfies hard constraints. Circuit breakers stop cascades; quality gates detect silent cross-component degradation; local gateways enforce side-effect policy; and verify-before-retry protects non-atomic actions.

## Negative results and gaps

- Endpoint safety does not imply safe intermediate execution.
- Stronger models do not uniformly improve fault tolerance.
- Closed-loop critique does not catch every semantic fault.
- Trace localization assumes sufficient logs and is not yet robustly demonstrated for multi-root failures.
- Policy enforcement trades off task completion, false intervention and latency.
- Reported MTTR gains can depend on weak baselines.
- Exactly-once tool effects require remote-service cooperation, not just model instructions.

## Next evidence needed

1. Independent replication of trace-level policy contracts.
2. Multi-root and missing-log root-cause localization.
3. Realistic non-atomic side-effect tests with idempotent and non-idempotent services.
4. Degraded-mode evaluation under common-mode control-plane failure.
5. Strong retry/backoff and deterministic workflow baselines.
6. Safe-utility frontiers under held-out operational profiles.
