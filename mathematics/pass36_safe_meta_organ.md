# Mathematical Formalization — Pass 36: Safe Meta-Organ

## 1. System state

Represent the persistent Holobiont configuration at step t as

\[
S_t=(V_t,E_t,R_t,M_t,P_t,A_t,\Theta_t),
\]

where:
- V: active organ instances and capability registry;
- E: communication and dependency graph;
- R: role specifications and routing policies;
- M: shared and local memory configuration;
- P: permissions and authorization policies;
- A: audit, provenance and version records;
- Θ: model parameters/adapters, where modification is separately governed.

A candidate mutation is a typed delta Δ_t. The production transition must be

\[
S_{t+1}=\operatorname{ApplyValidated}(S_t,\Delta_t),
\]

not arbitrary direct writes by a model.

## 2. Mutation classes

Define a mutation class c(Δ) in:
- C1: edge/link changes;
- C2: node activation/deactivation or role assignment;
- C3: prompt/role-template revision;
- C4: memory, skill or tool changes;
- C5: model adapter/weight changes;
- C6: permissions, evaluator or safety-policy changes.

The required approval strength should increase with mutation class and blast radius. C6 must not be writable by the same authority that proposes or evaluates ordinary changes.

## 3. Causal value

For a task set Q and fixed execution prefix z, define paired mutation value:

\[
\Delta U_{\mathrm{mut}}
=\mathbb{E}_{q,z}[U(q,z\mid do(\Delta))]
-\mathbb{E}_{q,z}[U(q,z\mid do(\varnothing))].
\]

The no-change arm must receive the same additional time, context and verifier budget. A sham mutation controls for the cost of an extra planning pass.

A mutation is useful only if its effect survives held-out tasks and resource matching. Report confidence intervals and per-domain effects, not only pooled averages.

## 4. Constrained objective

A candidate objective is

\[
\max_{\Delta}\quad
\mathbb{E}[\Delta U]
-\lambda_c C(\Delta)
-\lambda_l L(\Delta)
-\lambda_m M(\Delta)
-\lambda_o O(\Delta),
\]

subject to

\[
P(\text{safety violation}\mid S_t+\Delta)\le \epsilon_s,
\]
\[
P(\text{privacy/authorization violation})\le \epsilon_p,
\]
\[
\operatorname{GraphInvariant}(S_t+\Delta)=1,
\]
\[
\operatorname{PermissionInvariant}(S_t+\Delta)=1,
\]
\[
\operatorname{RollbackAvailable}(\Delta)=1.
\]

A scalar penalty is not a substitute for hard safety constraints when the mutation can authorize external actions, change evaluator rules or widen data access.

## 5. Safety and recovery metrics

- Mutation precision: fraction of accepted mutations with positive held-out causal value.
- Regression rate: fraction of accepted mutations that reduce protected-suite performance or violate constraints.
- Rollback success: probability of restoring all controlled state after a failed canary.
- Recovery time: time from detected regression to restored safe configuration.
- Blast radius: number of organs, memories, tools, permissions and downstream actions affected.
- Graph churn: normalized edge/node edit distance over a fixed task horizon.
- Diversity retention: change in behavioral/capability diversity, not merely role-name or embedding diversity.
- Evaluator independence: degree to which proposal and evaluation signals share model, data, reward and control dependencies.

## 6. Cumulative lineage risk

Let F_k be a harmful regression event caused by mutation k. Over T mutations,

\[
R_T=P\left(\bigcup_{k=1}^{T}F_k\right).
\]

If events were independent, a product expression could approximate the union risk, but self-evolving systems create dependencies: one bad mutation may weaken later evaluators or alter the mutation distribution. Therefore empirical lineage replay and dependency-aware risk estimation are required; multiplying per-mutation safety rates is generally unjustified.

## 7. Rollback condition

A rollback must restore more than the visible graph:

\[
\mathcal{R}(S_{t+1})\stackrel{?}{=}S_t
\]

where equality includes:
- active agents and versions;
- edges, visibility and routing;
- prompts, tools and adapters;
- memory/index/cache state;
- permission and authorization state;
- pending actions and external side effects;
- audit lineage.

For irreversible external actions, exact rollback may be impossible. Such actions need pre-commit authorization, idempotency and compensating procedures.

## 8. Distinguishing adaptation from learning

Let U_task be the utility gained from choosing a better topology for the current task, and U_cap be the capability change of an organ itself. A system may improve U_task while U_cap remains unchanged. Report them separately.

Prompt-role generation, edge pruning, agent spawning from an existing pool, adapter training and specialist regeneration are different intervention classes. They must not be aggregated under a single “self-improvement” metric.
