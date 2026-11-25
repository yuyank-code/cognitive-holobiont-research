# Mathematical Formalization — Pass 40
**Date:** 2026-11-25  
**Topic:** Information-conditional capability recovery.

## 1. Objects and assumptions

Let:
- \(K\) denote a target organ's capability, represented as a behavioral function or a member of a declared hypothesis class;
- \(R\) denote all information accessible to the recovery system after deletion;
- \(X\sim D\) be evaluation inputs from a held-out distribution;
- \(\widehat K=g(R)\) be the recovered behavior;
- \(B\) be the strongest declared fallback, such as a generalist, router or remaining-organ ensemble.

The recovery system may use only the declared components of \(R\). Checkpoints, adapters, data, teacher queries, hidden-state traces, gradients, task vectors, memory, tool outputs and repair hypernetworks must each be listed explicitly.

## 2. Information cannot be created by the recovery map

For any deterministic or randomized recovery process \(\widehat K=g(R,\epsilon)\), where \(\epsilon\) is independent recovery randomness,

\[
I(K;\widehat K)\leq I(K;R,\epsilon)=I(K;R).
\]

This is the data-processing inequality. It does not say that recovery is impossible whenever \(R\) is incomplete. It says the recovery process cannot extract information about K that is absent from R, apart from exploiting a prior or structure already encoded in the recovery algorithm.

For a finite capability-class identification problem with \(|\mathcal K|>1\), Fano's inequality gives a lower bound of the form

\[
P_e \geq \frac{H(K\mid R)-1}{\log |\mathcal K|},
\]

with the usual non-negativity and log-base conventions. This bound applies to a declared finite hypothesis class; arbitrary behavioral functions require a more careful task-distribution formulation.

## 3. Behavioral capability recovery

Let \(U_D(F)\) be independently measured utility of behavior F on held-out distribution D. Define:

\[
CR_D(\widehat K;B)=
\frac{U_D(\widehat K)-U_D(B)}
{U_D(K)-U_D(B)}.
\]

Interpretation:
- 0: no improvement over fallback B;
- 1: matches the original specialist's measured utility;
- between 0 and 1: partial recovery;
- above 1: exceeds the original on this metric, not necessarily equivalent;
- undefined/unstable when \(U_D(K)\approx U_D(B)\).

Always report numerator and denominator, confidence intervals, per-slice metrics and the raw utility. Do not clip values silently.

## 4. Separate exact parameter recovery from functional recovery

Exact parameter recovery:

\[
E_W = d(\widehat W,W^*)
\]

for a declared parameter distance d, meaningful only when architecture, parameterization and alignment are comparable.

Functional recovery:

\[
E_F = \mathbb E_{x\sim D}
\left[\ell\big(\widehat K(x),K(x)\big)\right].
\]

Distributional recovery:

\[
E_P = D_{\mathrm{beh}}\big(P_{\widehat K}(\cdot\mid X),P_K(\cdot\mid X)\big).
\]

These are not interchangeable. A functionally equivalent model may have very different weights; a close weight vector may still fail on rare inputs.

## 5. Information-source ablation

Represent the surviving information budget as:

\[
R=(R_{\text{base}},R_{\text{peer}},R_{\text{data}},
R_{\text{traces}},R_{\text{adapters}},R_{\text{teacher}},
R_{\text{hypernet}},R_{\text{memory}},R_{\text{tools}}).
\]

Use factorial removal interventions to estimate the marginal and interaction value of each source. In particular, test whether peer weights and peer-generated traces add information beyond a generalist model, public data and a generic repair hypernetwork.

A source should not be counted as “peer knowledge” if it is actually a hidden copy of the target checkpoint or a teacher response cache.

## 6. Resource and risk frontier

For each recovery method report:

\[
\mathbf C =
(C_{\text{train}},C_{\text{infer}},C_{\text{storage}},
C_{\text{data}},C_{\text{latency}},C_{\text{verification}},
C_{\text{privacy}},C_{\text{risk}}).
\]

A recovery method is not better merely because it has lower inference cost if it requires a large offline teacher, privileged checkpoint or expensive adapter-training phase.

## 7. Hypothesis for the Holobiont

Peer-assisted regeneration is useful only when:

1. surviving organs retain information about the lost capability;
2. the recovery system can identify and access that information;
3. a generated specialist generalizes beyond copied examples;
4. validation detects capability and safety regressions;
5. the recovery route is not compromised by the same failure that removed the original organ.

The first experimental question is to estimate \(I(K;R)\) indirectly through controlled ablations and predictive recovery, not to assume it is high because the organs are connected.
