# Mathematics Addendum — Pass 27: Causal Synergy, Dependence, and Recovery

**Date:** 2026-10-16. All expressions below are proposed evaluation definitions, not established universal laws.

## 1. Matched-budget marginal value of coupling

Let \(T\) be a communication/intervention policy, \(T_0\) the strongest feasible independent baseline, \(k\) a task family, and \(B\) a vector of total resources (all observable tokens, tools, verification, retries, latency, and cost). Define

\[
\Delta_k(T;B)=\mathbb{E}[U\mid do(T),k,B]-\mathbb{E}[U\mid do(T_0),k,B].
\]

\(U\) must be task-grounded utility or verified success, not vote share, number of messages, or a trace-derived synergy score. If the internal reasoning budget cannot be observed or matched, report the comparison as resource-unmatched.

A positive \(\Delta_k\) supports a task-conditional collaboration gain. It does not by itself establish a unique Holobiont mechanism; that requires comparisons with the strongest feasible single-agent, ensemble, and ordinary-MAS alternatives.

## 2. Edge effects and higher-order interactions

For a fixed base policy and total resource budget, let \(Q(S)\) be expected verified utility when the set of communication channels \(S\) is enabled. The context-specific marginal edge effect is

\[
\tau_e(S)=Q(S\cup\{e\})-Q(S).
\]

The pairwise interaction of channels \(e,f\) in context \(S\) is

\[
I_{ef}(S)=Q(S\cup\{e,f\})-Q(S\cup\{e\})-Q(S\cup\{f\})+Q(S).
\]

Positive \(I_{ef}(S)\) means the joint edge effect exceeds the sum of its separate effects for this outcome and context. It does not automatically mean novel cognition: it can reflect coordination constraints, resource interactions, or a particular benchmark’s mechanics. Estimate it with randomized edge interventions, multiple seeds, and ownership swaps; report uncertainty and interaction context.

## 3. Communication-induced regression

For agent \(i\), task instance \(x\), matched rollout/seed \(r\), let \(c_i^0(x,r)\in\{0,1\}\) indicate correctness without communication and \(c_i^T(x,r)\) correctness after topology \(T\).

\[
R_T=P(c_i^0=1,c_i^T=0),\qquad
G_T=P(c_i^0=0,c_i^T=1).
\]

\(R_T\) is the communication-regression rate and \(G_T\) the communication-improvement rate. Also report the paired net accuracy change, \(G_T-R_T\), with task/agent stratification. These rates distinguish helpful information transfer from conformity or correlated error even when majority accuracy changes little.

## 4. Dependency-aware panel confidence

Let \(V\) denote the panel vote/answer distribution; \(G^T\) the post-communication dependence graph; \(G^0\) the matched no-communication counterfactual graph; and \(H\) group-level dependency features (model family, role, answer cluster, common sources/exposures). A calibration model can be written as

\[
\hat p(\text{panel correct}\mid V,G^T,G^0,H,k).
\]

This is a predictive calibration target, not a causal guarantee. Validate ECE, Brier score, discrimination, selective risk, and calibration under held-out topology, task family, model family, and adversarially induced dependence. If \(G^0\) or candidate topologies require extra runs, include them in the resource budget.

## 5. Fault recovery decomposition

For injected fault class \(f\), separately estimate:
- \(D_f\): probability the fault is detected;
- \(C_f\): probability a detected local fault is corrected;
- \(K_f\): probability propagation is contained;
- \(S_f\): probability the overall task succeeds after injection;
- \(H_f\): collateral harm/false-alarm rate on clean cases.

These quantities are deliberately separate: \(D_f=1\) does not imply \(C_f=1\), and \(C_f=1\) does not imply \(S_f=1\). Report denominators and condition on baseline solvability, following the process-level motivation of MAS-FIRE.

## 6. Temporal invalidation

For a source fact superseded at time \(t_s\), let \(t_i\) be the time all dependent components are prevented from using it for new actions. Define invalidation lag \(L_i=t_i-t_s\). Define stale-action rate as

\[
S_{\mathrm{act}}=\frac{\#\{\text{executed actions critically dependent on superseded evidence}\}}{\#\{\text{executed actions}\}}.
\]

Measure retraction propagation separately from ordinary updates and distinguish dependent claims from genuinely independent corroboration. These are proposed operational metrics; no universal acceptable threshold is implied.

## 7. Preregistered rejection logic

A distinctive collective-synergy claim should be rejected if:
1. the task-utility gain vanishes against the strongest feasible baseline under matched total resources;
2. gains vanish after randomizing who owns decisive facts;
3. gains fail on held-out task families or independent replications;
4. structural synergy rises without verified task utility, or action-attribution scores do not survive removal/corruption interventions; or
5. privacy/authorization constraints are violated.

Do not combine utility, privacy, false rejection, calibration, and cost into a single score if a hard constraint is violated. Report Pareto trade-offs where policy thresholds are not fixed.
