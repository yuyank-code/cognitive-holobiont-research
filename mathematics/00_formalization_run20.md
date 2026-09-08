# Formalization Notes — Run 20

## 1. Replace communication gain with conditional information gain

Let S be a sender with private state X_S, receiver state X_R, task target Y, and latent message M. The relevant quantity is not merely

ΔAcc = Acc(Y | M) − Acc(Y)

because M may carry generic context or information available elsewhere.

Define the conditional sender-specific information gain:

I_sender = I(Y; M | X_R, Z)

where Z contains all non-sender information available to the receiver and all control variables. A practical causal estimate uses matched sender/example and mismatched/zeroed/random message interventions.

The Holobiont latent-transfer claim is therefore strongest when I_sender > 0 under receiver isolation and survives model/task replication.

## 2. Distributed cognition requires integration, not communication

Let A be information acquired from other specialists and G be the global task state that must be synthesized. Define an integration efficiency:

η_int = useful_global_information_recovered / information_acquired

A system can have high communication bandwidth B and high acquisition but low η_int. SILO-BENCH provides empirical motivation for treating η_int as a separate bottleneck.

## 3. Effective independence

Let K be nominal specialist count. Let C_ij denote causal dependence/failure correlation between specialists i and j. A conceptual effective-channel measure is

K_eff = 1 / Σ_{i,j} w_i w_j C_ij

under normalized weights, with the exact estimator left open. This is not yet claimed as a universal metric. It is a hypothesis: collective benefit should track effective independent evidence better than raw K.

## 4. Reliability should include graph dependence

For communication graph G and execution trajectory τ, define uncertainty as

U = U(Y | τ, G, E)

rather than U(Y | final output) alone. MATU motivates estimating uncertainty from trajectories and topologies. The Holobiont should test whether graph-aware uncertainty predicts correlated failure and calibration better than marginal confidence.

## 5. Regeneration information bound

Let K* be unique capability information held by a destroyed specialist. Let R denote all surviving distributed traces, generators, memory, and external information. Behavioral regeneration is impossible when

I(K* ; R) ≈ 0

for the task-relevant capability. Therefore regeneration experiments must manipulate I(K*;R) by controlled redundancy levels and measure behavioral equivalence, OOD robustness, calibration, conflict fidelity, and collateral regression.

## 6. Architecture objective

A provisional objective is

max U = Q_collective − λ_B B − λ_C Coupling − λ_F P_joint_failure − λ_P PrivacyLeak − λ_O CoordinationOverhead

subject to fixed total compute, memory, information, and redundancy budgets.

This is deliberately not an implementation prescription. It is a falsifiable decomposition of the claims into measurable terms.
