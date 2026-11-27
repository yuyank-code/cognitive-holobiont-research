# Falsification Framework — Pass 42: Graceful Degradation and Reliable Capability

The proposed contract-driven degradation architecture is not justified if any of the following occurs under representative held-out task/fault profiles:

1. It increases raw task completion only by permitting actions that violate hard authorization, evidence or safety constraints.
2. Its safe-completion rate is no better than a simpler deterministic gateway plus retry/rollback baseline at comparable cost.
3. Its mode selector frequently chooses full federation when required evidence or verification is unavailable.
4. Its degraded modes silently fabricate missing specialist evidence or treat a fallback response as equivalent to the unavailable organ.
5. Delegation can widen permissions or multiply a parent's remaining budget through concurrent child calls.
6. A timeout after dispatch can cause duplicate external effects because the runtime retries without checking postconditions or idempotency.
7. Component health remains green while cross-component semantic quality degrades and no quality gate detects it before user impact.
8. Root-cause localization gains disappear when logs are incomplete or multiple faults interact.
9. Heart/policy-root/journal failure disables local safety enforcement or forces the system into a permissive mode.
10. False interventions erase the useful-work advantage over whole-workflow halt.
11. Audit completeness cannot reconstruct the actual actions, versions, authority and evidence used.
12. The system cannot explain whether a partial result satisfies the task's declared degraded-output contract.

A positive result requires a Pareto improvement or a clearly justified trade-off across safe completion, useful degraded work, unsafe effects, false intervention, latency, cost and auditability. Uptime or endpoint accuracy alone is insufficient.

The strongest falsification test is a hidden-fault, multi-root, non-atomic-action evaluation with no oracle fault-origin alerts and with the control plane itself subject to failure.
