# Formalization Notes — Run 22

## 1. Conditional sender-specific information

Retain

I_sender = I(Y; M | X_R, Z)

where M is the sender message, X_R is receiver-private state, and Z contains all non-sender information and controls. The causal estimand should be approximated with matched sender/example, mismatched-example, zeroed, and moment-matched random interventions.

**New constraint:** report both I_sender and the total message effect. A large total effect with near-zero I_sender is not evidence for novel sender information.

## 2. Integration as a separate operator

Let A be information acquired by the collective and G the task-relevant global state. Define

eta_int = useful_global_information_recovered / information_acquired.

A useful architecture must maximize eta_int subject to bandwidth and coordination costs. This directly targets the SILO-BENCH/MAS-BENCH failure mode.

## 3. Diversity and selection

Let D denote candidate diversity and S the selector/integration quality. A provisional collective utility model is

U_collective = F(D, S, K_eff, B, C, P_joint).

The Selection Bottleneck hypothesis predicts a crossover: increasing D can decrease utility when S is below a task-dependent threshold, and increase utility when S is above it. This is a testable hypothesis, not a law.

## 4. Effective independent channels

Retain the candidate form

K_eff = 1 / sum_ij w_i w_j C_ij

with normalized weights w_i and dependence matrix C. The next methodological step is to compare statistical C_ij against intervention-derived failure dependence. A metric that predicts only representation similarity but not marginal utility/failure diversity is insufficient.

## 5. Topology-dependent reliability

For graph G and trajectory tau:

U_sys = U(Y | tau, G, E).

Add topology conductivity terms to the objective:

J = Q_collective - lambda_B B - lambda_C Coupling - lambda_F P_joint_failure - lambda_A AttackConductivity - lambda_O CoordinationOverhead.

The graph should be optimized under explicit common-mode and attack constraints, not accuracy alone.

## 6. Regeneration information bound

Let K* be unique capability information and R all surviving traces/generators/memory. If I(K*;R) is negligible, genuine recovery cannot be expected without external information. Regeneration experiments should therefore vary redundancy and surviving traces while evaluating behavior, OOD, calibration, conflict fidelity, and collateral regression.

## 7. Specialist identity as a causal state

Define an organ candidate i by a capability intervention signature S_i(t): the vector of behavioral effects caused by controlled ablations/substitutions/perturbations at time t. Persistent identity requires high temporal stability of S_i(t) while allowing internal parameter/representation drift.

This avoids equating organ identity with a fixed parameter block or routing label.

## Mathematical status

All quantities above are provisional research constructs. None is claimed to be a universal law or an implementation prescription.
