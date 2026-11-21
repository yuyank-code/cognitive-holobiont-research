# Experiment Backlog — Pass 36: Meta-Organ and Safe Structural Evolution

## E36-A — Initial planning vs runtime mutation (highest priority)

**Question:** Does editing the topology during a task add causal value beyond a strong task-conditioned initial router?

Arms:
1. Fixed hand-designed graph.
2. Strong task-conditioned initial planner, then frozen.
3. Initial planner plus bounded runtime mutation.
4. Initial planner plus sham mutation/equal extra planning pass.
5. Oracle topology upper bound.

Hold the task prefix, model pool, maximum agent count, tools, token budget, wall clock and verifier budget fixed. Randomize paired task instances and mutation assignment.

Measure answer utility, process reliability, mutation precision, latency, tokens, false repair triggers and regression.

## E36-B — Heterogeneous-organ transfer

Run E36-A in two strata:
- homogeneous agents instantiated from one backbone with different role prompts;
- genuinely heterogeneous specialist models with different training, model families or modalities.

Test whether topology/role policies learned on one stratum transfer to the other. Measure capability complementarity and failure correlation, not only score.

## E36-C — Persistent evolution under distribution shift

Train role/topology priors on task family A. Stream tasks from family B, then C. Compare:
- frozen architecture;
- per-task router without persistent memory;
- persistent role/topology cache;
- bounded cross-task evolution;
- periodic reset to a validated baseline.

Measure first-k adaptation, steady-state utility, forgetting, negative transfer, graph churn, cost and protected-suite regressions.

## E36-D — Longitudinal safety regression (SEABench-style)

Create upstream tasks that reward locally useful changes to controller rules, role prompts, tool policies, memory and routing. Later tasks test different recipients, permissions, privacy boundaries and safety constraints.

Compare evolving and frozen systems under paired seeds. Include benign pressure, misleading feedback and explicit adversarial attempts as separate conditions.

Measure task completion and safety separately. Do not collapse them into one scalar.

## E36-E — Evaluator independence and reward hacking

Compare:
- proposer evaluates itself;
- proposer and judge share a backbone;
- independent model judge;
- deterministic task-specific verifier;
- hidden held-out tests and externally recomputed metrics;
- human approval for high-impact changes.

Allow the proposer to inspect varying amounts of evaluator feedback. Measure confirmed reward hacks, false approvals, false rejections, exploit persistence and transfer to unseen tests.

## E36-F — Role collapse and specialist diversity retention

Track role behavior across generations using:
- capability profiles on held-out probes;
- error correlation;
- response/action distributions;
- domain-specific calibration;
- independent information contribution;
- robustness under perturbation.

Compare prompt-role novelty scores against actual capability separation. Test whether shared rewards or persistent role-cache reuse cause convergence.

## E36-G — Failure-driven reconfiguration

Inject:
- missing validator;
- broken communication link;
- duplicated state-changing actions;
- stale or hidden evidence;
- compromised organ;
- overloaded organ;
- unavailable specialist.

Compare no mutation, random mutation, fixed repair rules and Meta-Organ proposals. Use ground-truth fault labels for evaluation, but hide them from the controller.

Measure correct diagnosis, repair precision, task recovery, unsafe routing and blast radius.

## E36-H — Mutation rollback and interruption

Interrupt proposals at every stage: generation, validation, sandbox, canary, commit. Corrupt a graph delta, role specification, permission field and memory update. Test whether rollback restores graph, prompts, tools, memory, authorization, pending actions and audit lineage.

For external side effects, test idempotency and compensating actions rather than claiming exact rollback.

## Required controls

- Single model with matched compute.
- Best-of-K/self-consistency.
- Static specialist network.
- Task-conditioned router without persistence.
- AGP-style learned node/edge pruning.
- MetaGen-style dynamic roles/topology.
- MANTA-style runtime trace repair.
- AgentConductor-style feedback-driven topology.
- Frozen system with identical memory.
- Oracle topology as an upper bound.

## Pass criteria

A topology mutation should not be accepted merely because the final score rises in one benchmark. It must:
- beat a no-mutation arm on paired held-out tasks;
- retain the effect under compute/token/latency matching;
- pass protected safety and privacy suites;
- preserve specialist capability and useful diversity;
- have a tested rollback or compensating procedure;
- not rely on the proposer having access to the hidden evaluator.

The first experiment should be topology-only. Do not enable model-weight, permission, evaluator or constitutional mutation until structural evolution has passed these controls.
