# Mathematics Addendum — Pass 28: Effective Evidence, Protocol Value, Memory Identifiability

## Effective team size

\[
N_{\mathrm{eff}}=\frac{N}{1+(N-1)\rho},\qquad
\rho_N=cN^{-\beta},\qquad
R(N)=\frac{1}{1+c(N-1)N^{-\beta}}.
\]

This variance-matching proxy depends on an exchangeable/equicorrelation-style model. Heterogeneous graphs with shared retrieval, tools, or clustered failures may require a covariance or dependence-cluster model. Fit quality is not proof of causality or domain generality.

## Separate measures

\[
D_{\mathrm{ans}}=2^{H(A)},\qquad
N_{\mathrm{eff}}^{\mathrm{corr}}=\frac{N}{1+(N-1)\rho_{\mathrm{corr}}},\qquad
\Delta U=U_{\mathrm{intervention}}-U_{\mathrm{control}}.
\]

Answer entropy measures answer diversity; correctness dependence measures redundancy under its assumptions; delta U measures task utility. Distinct wrong answers can raise diversity without improving correctness. Shared item difficulty can inflate correctness correlation; estimate within-item dependence after conditioning on pre-interaction performance where feasible.

## Task-conditioned intervention value

\[
\Delta V(e\mid k,B)=
\mathbb{E}[U\mid do(e),k,B]
-\mathbb{E}[U\mid do(e_0),k,B]-C(e).
\]

Here k is task family, B fixes resource and information-access conditions, and e0 is a pre-registered control. U must be independently verified. Privacy and authorization are hard constraints.

For two edges in context S:

\[
I_{ef}(S)=Q(S\cup\{e,f\})-Q(S\cup\{e\})-Q(S\cup\{f\})+Q(S).
\]

This interaction is context-specific; positive interaction alone is not proof of novel collective intelligence.

## Memory estimand

\[
\Delta U_{\mathrm{mem}}=
\mathbb{E}[U\mid do(M=1),\mathcal{H}]
-\mathbb{E}[U\mid do(M=0),\mathcal{H}].
\]

A valid test requires a relevant prior record, an executing read path, authorized and temporally valid evidence, a later decision that can benefit, arms that differ only in the memory operation, within-run history preservation, cross-arm isolation, counterbalanced order, and uncertainty covering paired and between-run variation.

## Adaptive protocol value

\[
\Delta V_{\mathrm{router}}=
\mathbb{E}[U_{\mathrm{adaptive}}-U_{\mathrm{fixed}}]
-C_{\mathrm{routing}}-C_{\mathrm{verification}}.
\]

Compare on held-out scenarios under matched budgets. Report utility, latency, token/tool costs, failure recovery, privacy, and benign-evidence false rejection separately; publish any scalar weights and the Pareto frontier.
