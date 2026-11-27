# Mathematical Formalization — Pass 42: Reliability Contracts and Graceful Degradation

## 1. Execution-path admissibility

Represent an execution as a trajectory

\[
\xi=(s_0,a_0,o_1,s_1,a_1,\ldots,s_T).
\]

For each action \(a_t\), define:

\[
\operatorname{Adm}(a_t)=
I_t\land R_t\land D_t\land B_t\land P_t\land E_t,
\]

where:
- \(I_t\): actor identity and role are valid;
- \(R_t\): tool/action authority is sufficient and no broader than policy permits;
- \(D_t\): data and memory scope is authorized;
- \(B_t\): budget is available and reserved;
- \(P_t\): preconditions and state-version checks hold;
- \(E_t\): required provenance, evidence and approval are present.

A reliable path requires:

\[
\operatorname{Reliable}(\xi)=
\bigwedge_{t=0}^{T}\operatorname{Adm}(a_t).
\]

This is stricter than endpoint correctness. A final answer cannot erase an unsafe intermediate action.

## 2. Monotone delegation

Let a policy state contain a security profile, tool set, memory scope, remaining budget, materialization rule, approval predicate and evidence obligations.

For caller \(i\) delegating to callee \(j\), the child context must use:
- the stricter of caller and callee profiles;
- intersection of their tool permissions;
- intersection of their memory scopes;
- the smaller of caller remaining budget and callee cap;
- accumulated approval obligations;
- union of evidence obligations.

For concurrent children \(J_i\), reserve budgets atomically:

\[
b_i^{\mathrm{local}}+
\sum_{j\in J_i}b_{i\to j}
\le B_i^{\mathrm{remaining}}.
\]

Without atomic reservation, two parallel children can each be granted the same remaining parent budget. The formal rule prevents budget amplification only if the runtime actually enforces reservations.

## 3. Graceful mode selection

Let \(\mathcal M=\{M_0,M_1,M_2,M_3,M_4\}\) be full federation, communication-degraded, specialist-degraded, read-only/no-side-effects, and safe-pause/abstain.

Choose:

\[
m^*=\arg\max_{m\in\mathcal M}
\mathbb E[U(m,\tau)]
\]

subject to:
- hard safety and authorization invariants;
- evidence and provenance requirements;
- task-specific minimum quality;
- latency and resource constraints;
- no widening of delegated authority under degradation.

If no mode is admissible, choose safe pause/abstain. The utility function must not reward violating a hard constraint.

## 4. Safe availability

Report separate quantities:

\[
A_{\mathrm{reachable}}=P(\text{service responds}),
\]

\[
A_{\mathrm{safe}}=P(\text{valid task completion within deadline}),
\]

\[
A_{\mathrm{degraded}}=P(\text{useful partial result satisfying its contract}).
\]

Also report unsafe-effect probability, false intervention, detection/localization time, MTTR, audit completeness and cost. A system can have high reachability but low safe availability.

## 5. Non-atomic action semantics

For a tool call with possible timeout after dispatch:
1. assign an idempotency key;
2. dispatch through an effect gateway;
3. query the postcondition/state before retry;
4. retry only if the effect is known not to have occurred or the service guarantees idempotency;
5. otherwise reconcile or escalate.

Client retries alone cannot guarantee exactly-once effects when the remote service does not cooperate.

## 6. Reliability of dependency paths

For a strictly serial path with independent component success probabilities \(p_i\):

\[
P(\text{path success})=\prod_i p_i.
\]

This formula is only a baseline. Common-cause failures, shared policy roots, shared memory, shared tools and correlated model errors violate independence. A federation's reliability must include dependency and common-cause structure rather than multiplying marginal uptime figures.

## 7. Safe-utility frontier

Evaluate architectures over a vector:

\[
\mathbf R=
(Q_{\mathrm{safe}},Q_{\mathrm{degraded}},
P_{\mathrm{unsafe}},
P_{\mathrm{false\ block}},
T_{\mathrm{detect}},
T_{\mathrm{recover}},
L_{50},L_{95},C,B_{\mathrm{audit}}).
\]

Compare Pareto frontiers rather than collapse safety, task completion, latency and cost into one scalar.
