# Mathematics Addendum — Pass 24: Total-Cost Causal Evaluation

## 1. Governed value of information

Let \(G_t\) denote the current governance/state ledger, \(Y\) the task outcome, and \(\mathcal Q(G_t)\) the set of policy-permitted queries.

\[
\operatorname{GVOI}(q)=
\mathbb E[U(Y)\mid q,G_t]-
\mathbb E[U(Y)\mid G_t]
-\lambda_b B(q)-\lambda_\ell L(q)-\lambda_v V(q)-\lambda_p P(q),
\quad q\in\mathcal Q(G_t).
\]

Here \(B\) is communication cost, \(L\) latency, \(V\) verification effort, and \(P\) privacy/governance risk. This is a decision criterion, not a guarantee that the expected value is estimated accurately. If uncertainty is too high, the controller should abstain or seek external verification.

## 2. Versioned evidence state

Represent an item as

\[
z=(c,o,t_w,s,v,\pi,\mathcal P,\mathcal C,\mathcal D)
\]

where \(c\) is the claim, \(o\) is write-time origin/authority binding, \(t_w\) is write time, \(s\) is scope, \(v\) is the validity interval or version, \(\pi\) is provenance, \(\mathcal P\) parent evidence IDs, \(\mathcal C\) contradiction links, and \(\mathcal D\) dependent claims/actions.

Action-time eligibility is

\[
E(z,a,t)=
\mathbf 1[\mathrm{authorized}(z,a)]
\mathbf 1[\mathrm{scopeValid}(z,a)]
\mathbf 1[\mathrm{timeValid}(z,t)]
\mathbf 1[\mathrm{originValid}(z)].
\]

If \(E=0\), the item cannot support action without a new validation path. Retraction of an item triggers re-evaluation of descendants; it does not automatically erase independent corroboration.

## 3. Resource vector and synergy

\[
\mathbf B=(B_{\mathrm{reason}},B_{\mathrm{message}},B_{\mathrm{prompt}},
B_{\mathrm{memory}},B_{\mathrm{tool}},B_{\mathrm{verify}},L,\$).
\]

The provisional coalition advantage is

\[
\Gamma_H=Q(H\mid\mathbf B,\mathcal I,\mathcal G)-
\max_{m\in\mathcal M}Q(m\mid\mathbf B,\mathcal I,\mathcal G),
\]

where \(\mathcal I\) is the information-ownership structure and \(\mathcal M\) contains the best feasible single-agent, ensemble-selection, fixed-communication, adaptive-routing, and verified-shared-context alternatives.

A positive \(\Gamma_H\) is not enough to establish causal synergy if budgets are unobserved or baseline quality is weak. Require sender/message/action interventions and replication on held-out task families.

For a message \(m\), estimate a local intervention effect as

\[
\Delta_m=\mathbb E[U\mid do(m=m_{\mathrm{observed}})]-
\mathbb E[U\mid do(m=m_{\mathrm{ablated/replaced}})].
\]

Use randomized ablation/replacement and uncertainty intervals; do not infer causal contribution from a trace graph alone.

## 4. Cost metric correction

Communication efficiency alone,

\[
\mathrm{Eff}_{msg}=\frac{\mathrm{task\ score}}{\mathrm{message\ tokens}},
\]

can improve while total cost rises because local reasoning, prompts, verification, and tool calls are excluded. Report this metric only alongside total observed resource use and clearly label unobserved components.
