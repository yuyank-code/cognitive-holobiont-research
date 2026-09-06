# Mathematical Revision — 2026-09-07

## 1. Effective channel count

Raw specialist count N is replaced by an effective channel count K_eff, motivated by recent information-theoretic MAS scaling work.

Let Z_i denote the evidence-bearing output/state of specialist i. A simple dependency-aware proxy is based on the covariance/correlation matrix R of standardized specialist evidence:

K_eff = (tr R)^2 / tr(R^2).

This is only a proxy. It should not be treated as a universal measure of cognition because R depends on the chosen representation and task. Behavioral and intervention-based estimates must accompany it.

Properties:
- K_eff <= N for a positive semidefinite correlation matrix.
- Independent, equally weighted channels give K_eff approximately N.
- Highly correlated channels drive K_eff toward 1.

The key research hypothesis is that collective benefit should saturate with K_eff rather than N.

## 2. Communication coupling

Let D_0 be a pairwise divergence measure before communication and D_c after communication. Define a coupling ratio:

C = D_c / D_0.

C < 1 indicates homogenization under the selected metric; C > 1 indicates diversification. This is a measurement convention, not a causal law. It must be evaluated jointly with task accuracy and failure correlation.

A better Holobiont objective is therefore a Pareto problem:

maximize  U = capability gain - lambda_B bandwidth - lambda_F correlated-failure risk

subject to K_eff >= K_min and calibrated risk <= epsilon.

## 3. Dependency-aware evidence fusion

Let p_i be specialist confidence and A_ij a dependency estimate between specialists i and j. Naive voting assumes independence and can overcount correlated evidence.

A first-order effective evidence weight can be represented as:

w = (A + tau I)^(-1) p

with normalization/regularization chosen for numerical stability. This is not proposed as a final fusion rule; it encodes the principle that highly dependent evidence should contribute less marginal weight.

## 4. Novel sender-specific information

For sender-private variable X, receiver state R, and controls C, the target quantity is conditional information transfer:

I(X; R_after | R_before, C).

The empirical design must additionally compare valid paired messages with sender/example-mismatched, other-example, zero, and bandwidth-matched random messages. Positive end-task gain without a positive paired-message effect is not sufficient evidence for novel transfer.

## 5. Regeneration bound

Let K be unique capability information available only to a destroyed specialist. Let S be all surviving system state, including memories, adapters, generators, and other specialists. If:

I(K; S) is insufficient for the required behavioral equivalence,

then no internal reconstruction procedure can recover K without external information. The practical problem is therefore to maximize recoverable capability information I(K; S) while minimizing redundancy cost and common-mode correlation.

## 6. New theoretical question

The central mathematical problem is now a constrained distributed-coding problem:

maximize recoverability R(K|S) and collective utility U
while minimizing bandwidth B, storage M, coupling C, and joint failure probability P(F_1,...,F_m).

This reframes the Holobiont's strongest original intuition—regeneration through distributed structure—without assuming information can be created after destruction.

## Status

These equations are research abstractions and measurement proposals, not validated laws of the Holobiont. They require empirical calibration, counterexamples, and comparison with established ensemble/MoE/distributed-systems theory before being used for implementation decisions.
