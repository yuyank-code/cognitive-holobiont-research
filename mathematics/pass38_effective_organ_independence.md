# Mathematics — Effective Organ Independence and Common-Mode Failure
**Pass 38 · 2026-11-23**

## 1. Correctness dependence

For task domain d, failure mode f and evaluation item q, define:

X_i(q,d,f) in {0,1}

where X_i=1 if organ i completes the specified function correctly under the intervention. Let R^(d,f) be the correlation matrix of X across items.

For N equally competent organs with common pairwise correlation rho, the variance of the mean correctness fraction is:

Var(mean X) = p(1-p) [1 + (N-1)rho] / N

Equating this with the variance of N_eff independent organs gives:

N_eff = N / [1 + (N-1)rho]

This is the exchangeable, equal-competence result in Morante & Romero García-Rubio (2026). It is a variance-equivalent sample size, not a count of unique capabilities or information sources.

## 2. General equal-variance correlation matrix

For equal weights and standardized correctness variables:

N_eff = N^2 / (1^T R 1)

For normalized aggregation weights w (sum_i w_i=1):

N_eff(w) = 1 / (w^T R w)

This is meaningful only relative to the chosen correctness variables, evaluation distribution and weighting rule. It can be task- and perturbation-specific.

For unequal marginal variances, use covariance matrix Sigma and state the reference variance explicitly. One possible variance-equivalent convention is:

N_eff_var(w) = [sum_i w_i Sigma_ii] / [w^T Sigma w]

With independent equal-variance agents and equal weights, this returns N. Other reference conventions are possible; report the convention rather than hiding it.

## 3. Functional complementarity is different

For a coalition S and external task utility U:

DeltaU_i(S) = U(S union {i}) - U(S)

Estimate this by randomized ablation and ownership swaps. A specialist can have low or undefined same-task error correlation with an unrelated organ while still contributing high unique task utility.

Conditional mutual information may be a secondary diagnostic:

I(Y; E_i | E_S)

but information is not necessarily actionable, correctly interpreted, authorized or safe. External task utility and causal intervention remain primary.

## 4. Common-mode dependency model

Let G_dep=(V_dep,E_dep) represent shared dependencies: base weights, training data, distillation teacher, alignment, system prompt, evaluator, memory, codec, hypernetwork, tools, credentials, network and orchestrator.

For failure mode f, let A_f be the set of dependencies it compromises and let O(A_f) be the affected organs. Measure:
- failure incidence within O(A_f);
- conditional loss of system utility;
- recovery time and recovery quality;
- whether unaffected evidence paths remain;
- whether the repair path shares the compromised dependency.

Pairwise correlation is insufficient for coalition-level or higher-order common-mode events. Fault injection is required.

## 5. Distinguish three diversity objectives

- Capability diversity: broadens the set of tasks/evidence the collective can handle.
- Response diversity: reduces synchronized failures among components serving the same or overlapping function.
- Process/dependency diversity: reduces shared causes across models, evaluators, memory and infrastructure.

A resilient design must optimize these separately and report trade-offs.
