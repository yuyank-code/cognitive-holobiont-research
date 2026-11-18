# Mathematics Addendum — Pass 33: Recoverability, Repair and Byzantine Containment

## 1. Functional recovery is not exact weight reconstruction

Let O_j be the original specialist and O_hat_j a candidate replacement.

Parameter distance can be misleading because neural networks may implement similar functions with different parameterizations. Use held-out behavioral distance:

\[
D_{\mathrm{func}}(O_j,\hat O_j)
=\mathbb{E}_{x\sim\mathcal D_{\mathrm{heldout}}}
[d(O_j(x),\hat O_j(x))].
\]

Also report task utility, calibration, robustness, latency and energy separately. Exact weight recovery is a separate metric and is meaningful only when architecture and parameter alignment are controlled.

## 2. Capability recovery under surviving information

Let K_j denote the task-relevant capability information of the original organ. Let Z_survive contain all information accessible after deletion: surviving organs, memories, adapters, logs, bridges, hypernetwork state, training data and provenance.

Define the achievable recovery envelope:

\[
\mathcal R^*(Z_{\mathrm{survive}})
=\sup_{\hat O\in\mathcal A(Z_{\mathrm{survive}})}
\mathbb E[U(\hat O;\mathcal D_{\mathrm{heldout}})].
\]

This is not assumed to be monotonic in the number of surviving organs: a larger network can also contain correlated or poisoned information. Every experiment must inventory what remains accessible. Hiding a checkpoint while leaving a distilled copy, teacher activations or target-specific dataset available is not a valid test of regeneration from partial knowledge.

An information-theoretic impossibility check should ask whether the surviving state contains information that distinguishes the lost capability from plausible alternatives. If not, recovery cannot systematically outperform the relevant prior or external-data baseline.

## 3. Repair as a multi-objective problem

For repair parameters theta:

\[
\min_{\theta}
\left(
L_{\mathrm{defect}}(\theta),
L_{\mathrm{preserve}}(\theta)
\right)
\]

subject to hard safety, privacy, provenance and authorization constraints.

Do not report only one scalar repair score. Publish the Pareto frontier between defect reduction and preservation of unaffected capabilities. Include a false-repair metric: probability that a healthy component is modified or quarantined.

## 4. Net value of recovery

\[
\Delta U_{\mathrm{recover}}
=U(\hat O_j;\mathcal D_{\mathrm{heldout}})
-U(O_{\mathrm{fallback}};\mathcal D_{\mathrm{heldout}})
-C_{\mathrm{recovery}}.
\]

C_recovery includes training/inference compute, latency, bandwidth, memory, verification, privacy leakage and operational risk. Compare against the best feasible checkpoint, distillation, retraining and fallback baselines.

## 5. Mutation admission with recoverability

Let s be the current state and m a proposed persistent mutation. Admit only if:

\[
\operatorname{Improve}(m,s)\geq \tau_U
\land
\operatorname{Recoverable}(m,\mathcal S_{\mathrm{counterfactual}})\geq \tau_R
\land
\operatorname{Safe}(m)=1.
\]

Recoverability should be evaluated across changed dependencies, concurrent updates, partial writes, crash points and future states in which the mutation is obsolete. Store the pre-state or recovery witness and verify observational equivalence after rollback.

## 6. Receiver-side evidence filtering

For receiver i evaluating message m_j, let:

\[
s_{i\to j}=\phi_i(x,m_j).
\]

The score is produced by the receiver, not supplied by the sender. This reduces one attack surface—falsified sender confidence—but does not make phi_i a truth oracle. Measure:
- false acceptance of misleading messages;
- false rejection of correct minority evidence;
- evaluator calibration;
- performance under correlated evaluator errors;
- graph robustness under the stated local-fault assumptions;
- communication and inference cost.

## 7. Resource-matched comparison

For every architecture A, report a resource vector:

\[
B(A)=(C_{\mathrm{train}},C_{\mathrm{infer}},M,BW,L,V,I),
\]

where C_train is training compute, C_infer inference compute, M memory, BW communication bandwidth, L latency, V verifier budget, and I information access. Claims of superiority should compare Pareto frontiers under matched or explicitly normalized budgets, not only task accuracy.
