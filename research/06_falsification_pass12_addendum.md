# Falsification Framework — Pass 12 Addendum — 2026-09-19

## New pre-registered-style tests

1. **Decentralization ablation:** compare DeLM-like decentralized execution against centralized orchestration with identical models, decomposition, verified-state reads/writes, verifier calls, and total compute. If the decentralized topology has no residual benefit, decentralization is not itself a demonstrated mechanism.
2. **Information-market test:** agents declare private facts/uncertainties and request candidate facts. Compare marginal-information routing against random, broadcast-all, semantic-similarity, and request-all policies at equal communication budget.
3. **Coalition-synergy test:** measure `U(A,B)-U(A)-U(B)+U0` on tasks where no single agent can solve from its private view. Require replication across model families and a centralized model given equal total information.
4. **Topology robustness:** randomly and adversarially perturb the topology controller, edges, shared state, and reputation signals. Report collective failure correlation and K_eff rather than only average accuracy.
5. **Verification independence:** compare one shared verifier, replicated identical verifiers, heterogeneous verifiers, and externally grounded checkers. A replicated common rule does not count as independent evidence.
6. **Process-vs-answer validation:** test whether metamorphic trace failures predict held-out semantic failures better than final-answer judging. If not, trace validation should remain a secondary diagnostic.
7. **Task-anchoring intervention:** measure objective drift over long horizons with and without explicit task anchors, state snapshots, and termination policies. Require improvement without suppressing useful exploratory branches.
