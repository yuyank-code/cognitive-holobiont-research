# Mathematical Formalization — Collective Value and Budget Parity
**Pass 37 · 2026-11-22**

## 1. Task-conditioned architecture value

Let task family descriptor be
\[
\tau=(p,d,c,t,h,e,v),
\]
where:
- \(p\): exploitable parallelism;
- \(d\): dependency depth / sequential interdependence;
- \(c\): context saturation or fragmentation risk;
- \(t\): tool density and external-state interaction;
- \(h\): uncertainty/search-space entropy;
- \(e\): complementarity of evidence or expertise across components;
- \(v\): independent verification capacity.

Let architecture \(a\) be one of: single agent, multi-output/self-conditioning, best-of-K, MoE/router, independent ensemble, centralized MAS, decentralized MAS, hybrid MAS, or task-conditioned federation.

The value of an architecture must be measured against a strong task-appropriate baseline:
\[
\Delta Q(a,\tau,\mathbf B)
=\mathbb E[Q\mid a,\tau,\mathbf B]
-\max_{b\in\mathcal B_0}\mathbb E[Q\mid b,\tau,\mathbf B],
\]
where \(\mathcal B_0\) contains the single-model, ensemble, MoE and conventional workflow baselines.

## 2. Resource parity is a vector, not one scalar

Define
\[
\mathbf B=(F,T_{in},T_{out},L,M,W,I,V_c),
\]
where:
- \(F\): model compute / FLOPs or an explicitly stated proxy;
- \(T_{in},T_{out}\): total input and output tokens across all calls;
- \(L\): wall-clock latency;
- \(M\): memory/context capacity;
- \(W\): communication bandwidth;
- \(I\): external information and tool access;
- \(V_c\): verification/evaluator budget.

No experiment can always equalize every coordinate simultaneously. Report the full resource vector and evaluate a Pareto frontier. A system is not compute-matched merely because each agent has the same per-call token limit.

## 3. Net federation value decomposition

A useful bookkeeping identity is:
\[
G_{net}=G_{parallel}+G_{complement}+G_{verify}+G_{resilience}
-C_{comm}-C_{fragment}-C_{sync}-C_{reconcile}-C_{correlated}.
\]
This is a decomposition hypothesis, not a universal additive law. Each term must be operationalized in a particular experiment.

The federation is worthwhile only when positive task and resilience gains exceed the coordination and resource costs at the relevant operating point.

## 4. Causal interaction / superadditivity

For two organs \(i,j\) and a fixed background set \(S\), define the factorial interaction:
\[
\mathcal I_{ij}(S)=Q(S\cup\{i,j\})-Q(S\cup\{i\})-Q(S\cup\{j\})+Q(S).
\]
A positive value suggests a positive interaction, but it is not proof of information synergy unless total budgets, information access, call counts, selection and verification are controlled.

Required controls:
- replace removed agents' budget with an equal-budget single model or a neutral compute allocation;
- run ownership swaps for private evidence;
- compare against best-of-K and single-model multi-output;
- use an external evaluator;
- repeat across task instances and model seeds.

## 5. Information complementarity

For target answer or task-relevant variable \(Y\), task context \(X\), and organ messages \(M_i,M_j\), conditional mutual information can measure additional predictive information:
\[
I(Y;M_i\mid X,M_j).
\]
For two sources, a pre-registered partial-information-decomposition (PID) estimator can separate unique, redundant and synergistic information. For more than two sources, PID definitions are not unique; the chosen decomposition and estimator must be declared in advance.

Information synergy is not identical to utility synergy. A message can carry synergistic information that the final decision-maker fails to use, or improve accuracy through extra compute without transferring unique information.

## 6. Effective evidence-channel count

A descriptive correlation-based statistic may be:
\[
K_{eff}=\frac{(\operatorname{tr}C)^2}{\operatorname{tr}(C^2)},
\]
where \(C\) is a covariance matrix of calibrated error or evidence features across organs. This participation-ratio statistic is a proxy for statistical diversity only. It does not establish causal independence and can be misleading if the measured representation omits common failure causes.

Causal checks require interventions: correlated fault injection, shared-data removal, ownership swaps, model-family replacement and source ablation.

## 7. Task-conditioned architecture selection

A router can estimate:
\[
\widehat{G}(a\mid\tau,\mathbf B)
=\widehat{G}_{task}
-\lambda_c C_{comm}
-\lambda_l C_{latency}
-\lambda_r R_{error}
-\lambda_s R_{safety}.
\]
Safety and authorization should be hard constraints, not merely weighted penalties. The router should abstain from federation when expected gains are uncertain or negative.

The empirical ~45% single-agent baseline pattern reported in one study is not a constant in this equation. Any decision boundary must be learned and validated on held-out task families.
