# Pass 12 Mathematical Note — Information-Market Coordination

## 1. State
Each specialist i has private state S_i and public/shared state Z. A communication action a_i consists of payload choice, recipient set, timing and optional request/response.

## 2. Marginal information value
Define the expected utility gain of an action conditioned on receiver state:

`V_i(a_i | Z) = E[U(Y_hat | Z, a_i) - U(Y_hat | Z)] - Cost(a_i)`.

The key hypothesis is that communication should be allocated by estimated marginal value rather than message size or semantic similarity.

## 3. Unique contribution
For a task H requiring distributed information, define:

`U_i = U(H | S_1,...,S_N) - U(H | S_{-i})`.

This is an intervention-style quantity only if the removal procedure preserves all non-i information and protocol conditions. It is not valid to infer uniqueness from correlations alone.

## 4. Coalition synergy
For two information holders A and B:

`Synergy(A,B) = U(H | A,B) - U(H | A) - U(H | B) + U_0`.

Positive synergy is a candidate signature of genuinely compositional distributed computation. Negative values indicate redundancy/interference. Higher-order coalitions should be tested because pairwise synergy can miss distributed algorithms requiring three or more parties.

## 5. Coupling penalty
Let C denote empirical communication-induced dependence (e.g. change in failure correlation or conditional representational similarity after interaction). A provisional objective is:

`J(pi) = E[U] - beta B - gamma C - delta Fcorr - eta Vcost`.

Here B is communication budget, C is coupling, Fcorr is correlated-failure risk, and Vcost is verification cost. Coefficients are design parameters; this is a research objective, not a derived optimality theorem.

## 6. Core theorem-like conjecture to test
A Holobiont advantage should require all of the following under matched resources:

1. at least one positive marginal unique contribution `U_i > 0`;
2. a non-trivial coalition synergy term for tasks designed around complementary private information;
3. advantage survives centralized/MoE/MAS baselines with equal information and compute;
4. ablation of the critical private information channel causes a corresponding performance loss;
5. the advantage does not disappear after accounting for topology-controller and verification budgets.

This formulation is intended to convert the vague claim of “collective intelligence” into measurable causal and resource-constrained quantities.
