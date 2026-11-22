# Experiment Backlog — Federation Advantage
**Pass 37 · 2026-11-22**

## Experiment 1 — Matched-resource architecture frontier (highest priority)

**Question:** Does the proposed federation improve quality, reliability or resilience beyond the best simpler architecture at the same resource envelope?

Compare:
1. single strong model;
2. single model with multi-output/self-conditioning;
3. best-of-K / self-consistency;
4. MoE or learned model router;
5. homogeneous MAS;
6. heterogeneous MAS;
7. task-conditioned federation;
8. human-designed topology as a non-deployable upper bound.

Run several budget regimes rather than one scalar cap:
- equal total input/output tokens;
- equal measured compute or API cost;
- equal wall-clock latency;
- equal context and information access;
- equal verifier/tool budgets.

Report Pareto curves and all resource dimensions. Pre-register the primary metric and multiple-comparison handling.

## Experiment 2 — Private-evidence partition and ownership swap

Create tasks where organs receive disjoint, task-relevant evidence fragments. The evidence is unique to each owner and cannot be reconstructed from public context.

Conditions:
- single model sees the union of evidence;
- single model receives an equally compressed union;
- independent organs return answers without communication;
- organs exchange structured evidence;
- organs use learned latent bridges;
- best-of-K samples the same evidence;
- task-conditioned federation selects/routs evidence.

Then swap which organ owns each evidence fragment without changing model weights. If gains follow the evidence rather than the model identity, the system is transferring information; if they follow the model, capability differences are implicated.

## Experiment 3 — Factorial heterogeneity × communication

A 2×2 design:
- homogeneous models, no communication;
- homogeneous models, communication;
- heterogeneous models, no communication;
- heterogeneous models, communication.

Add best-of-K and single-model multi-output controls. Measure unique evidence recovery, error correlation, calibration, task utility and cost. Do not infer heterogeneity from role labels alone.

## Experiment 4 — Task-structure crossover

Use matched tasks with controlled variation in:
- parallel fraction;
- dependency depth;
- context saturation;
- tool density;
- evidence complementarity;
- uncertainty/search entropy;
- verification availability.

Test whether a learned architecture selector predicts which topology wins on held-out task families. Include sequential and compact-context tasks where single-agent is expected to be competitive.

## Experiment 5 — Orchestration information-preservation audit

Use task DAGs with known dependencies. Measure:
- missing critical transfers;
- lossy compression of essential facts;
- branch outputs omitted during synthesis;
- duplicate or redundant work;
- critical-path delay;
- final answer changes from correct to incorrect;
- verifier recovery of dropped information.

Use OrchBench-like deterministic simulation only as an initial screen, then validate with real worker executions.

## Experiment 6 — Emergence metric validity

Measure PID-style alignment, redundancy and synergy on a multi-agent task suite. Test whether these metrics predict externally scored utility after controlling for:
- total compute;
- number of samples;
- base-model strength;
- task difficulty;
- communication volume;
- selection quality.

Include negative-control groups with synchronized outputs but no complementary evidence. If a high synergy score does not predict utility, it must not be used as a system success metric.

## Experiment 7 — Long-horizon stateful task

Run a multi-stage environment with changing state, partial observability, memory and tool feedback. Compare persistent organs with ephemeral task agents and a single long-context controller. Track:
- state drift;
- context loss;
- handoff errors;
- cumulative latency/cost;
- recovery after organ dropout;
- retained specialist capability;
- performance after task distribution shift.

## Experiment 8 — Fault and resilience value

Inject independent and correlated failures:
- one specialist unavailable;
- communication edge broken;
- shared data source corrupted;
- same-family model error;
- orchestrator compromised;
- verifier unavailable.

Measure service degradation, safe abstention, error amplification, recovery time and residual task utility. A federation's resilience value should be measured separately from its normal-operation accuracy.

## Minimum evidence before implementation

Do not begin a large organ network until:
- one task family shows a reproducible positive resource-adjusted advantage;
- the gain survives best-of-K and single-model multi-output controls;
- private-evidence interventions demonstrate causal information transfer;
- the router identifies when not to use the federation;
- a failure experiment demonstrates an advantage not reproduced by a conventional backup or ensemble.
