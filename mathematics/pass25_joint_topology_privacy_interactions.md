# Mathematics Addendum — Pass 25: Joint Topology, Privacy, and Interaction Effects

## 1. Constraint-first design

Let π denote a complete collective policy (elicitation, routing, memory admission, verification); (U(π)) is task utility; (L(π)) is measured privacy leakage under a declared threat model; (F(π)) is the false-rejection rate for benign, decision-relevant evidence; and (C_k(π)) are resource costs.

A more faithful objective is:

[
max_{pi}; mathbb{E}[U(pi)]
]

subject to

[
L(pi)le epsilon,qquad
F(pi)le delta,qquad
C_k(pi)le B_k,
]

plus hard authorization and information-flow rules. This is preferable to a single weighted sum when some privacy or disclosure requirements are non-negotiable. If thresholds are policy choices rather than known constants, publish the full utility–leakage–false-rejection Pareto frontier.

## 2. Governed value of information

For a candidate query (q), define:

[
operatorname{GVOI}(q)=
mathbb{E}[Delta Umid q,mathcal{S}_t]
-lambda_c C(q)-lambda_v V(q)
]

only for queries that satisfy the authorization and sensitivity policy. A positive estimated value does not override a hard disclosure prohibition. Query-value estimates should include uncertainty and be calibrated against realized task utility, not merely disagreement or message novelty.

## 3. Versioned evidence with dependency-aware admission

An evidence record should preserve claim, origin, authorization scope, write time, validity/version, source lineage, parent evidence IDs, dependence clusters, contradictions, and downstream claims/actions. Correlated reports must not be counted as independent corroboration merely because they arrive through different agents or modalities.

Retraction invalidates descendants that depend on the retracted source, while genuinely independent evidence remains eligible for separate evaluation.

## 4. Local edge effects vs coalition interactions

Let (Q(S)) be expected task utility when the set of communication channels (S) is enabled under a fixed policy and resource budget. The marginal effect of edge (e) in context (S) is:

[
	au_e(S)=Q(Scup{e})-Q(S).
]

For two edges (e,f), the local interaction effect is:

[
I_{ef}(S)=Q(Scup{e,f})-Q(Scup{e})-Q(Scup{f})+Q(S).
]

(I_{ef}(S)>0) indicates a superadditive interaction in that context; (I_{ef}(S)<0) indicates redundancy/interference. These effects depend on (S), task distribution, and policy, so they are not intrinsic fixed properties of edges.

Single-edge ablation estimates (	au_e(S)) but can miss (I_{ef}(S)) and higher-order effects. Exhaustive subset evaluation is usually infeasible; use randomized pairwise/coalition sampling, pre-registered selection rules, multiple seeds, and uncertainty intervals.

## 5. Resource-matched coalition advantage

[
Gamma_H =
mathbb{E}[Umid do(H),mathbf{B},mathcal{I},mathcal{P}]
-max_{minmathcal{M}_{mathrm{feasible}}}
mathbb{E}[Umid do(m),mathbf{B},mathcal{I},mathcal{P}],
]

where (mathbf{B}) includes reasoning, prompt/context, message, tool, memory, verification, latency, and monetary budgets; (mathcal{I}) is information ownership; and (mathcal{P}) contains authorization and leakage constraints. Baselines must be feasible under the same constraints. A positive estimate requires held-out replication and cannot be inferred from graph attribution alone.

## 6. Separate security and utility metrics

At minimum, report:
- clean-task utility;
- utility under attack;
- write admission rate for malicious evidence;
- retrieval/action support from poisoned descendants;
- benign evidence false-rejection rate;
- private-information extraction rate under specified attacker placements;
- total resources and latency;
- intervention-estimated task contribution.

This prevents a reduction in attack success from being mistaken for a universal improvement in task utility.
