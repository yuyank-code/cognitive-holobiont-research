# Open Problems

This document tracks questions that remain unresolved after literature review. Items should be promoted, resolved, weakened, or split as evidence accumulates.

## Highest-priority open problems

- Generalization of causal sender-specific latent transfer across architectures, tasks, and private-information regimes.
- Whether latent channels provide a net advantage over text at equal information, compute, latency, and security budgets.
- Maximum reliable latent communication distance between independently specialized models.
- Functional definition of a cognitive organ when causal circuits are distributed or rewired across model scales.
- Optimal parameter-sharing ratio for cooperation versus specialization.
- Prevention of specialist homogenization under continuous communication.
- Information-theoretic requirements for distributed capability recovery after specialist destruction.
- Whether behaviorally equivalent regeneration can preserve rare/OOD capabilities and calibration.
- Practical limits of hypernetwork-based generation under large target models and conflicting priors.
- Fault tolerance under correlated/common-mode failures, especially shared generators, routers, memory, evaluators, and latent communication hubs/codecs.
- Reliable detection of Byzantine or malicious specialists and collusive truthful-but-misleading coalitions.
- Consensus mechanisms that preserve useful minority information without amplifying ungrounded disagreement.
- Capability-aware abstention and termination under shared uncertainty.
- Distributed memory integrity and recovery.
- Safe autonomous topology modification and topology-level attack resistance.
- Safe recursive self-improvement without irreversible capability loss or distributional overfitting.
- Whether dynamic-weight recursion generalizes beyond its training distribution.
- Empirical distinction between Holobiont behavior and an expensive ensemble/MoE/multi-agent system.
- Compute-, communication-, memory-, and redundancy-matched novelty tests against strong single-agent multi-output/self-conditioning baselines.
- Operational definitions of identity and continuity that do not rely on unsupported consciousness claims.
- Whether task-relevant latent information can be estimated robustly enough to serve as a routing/communication objective rather than a post-hoc analysis metric.
- Whether centralized latent hubs improve system-level scaling more than they increase correlated failure and security exposure.

## Newly sharpened theoretical questions

1. What is the minimum mutual information about a destroyed capability that must remain distributed for a target recovery fidelity?
2. Is there a non-trivial Pareto frontier between sender-specific information gain, privacy leakage, and coupling-induced failure correlation?
3. Under what graph/topology conditions does adding an edge increase collective information while decreasing epistemic diversity?
4. Can a stable meta-controller provably bound capability regression while still allowing useful architecture evolution?
5. What statistical test distinguishes useful minority hypotheses from merely noisy disagreement?
6. Can latent communication be evaluated by causal task information rather than raw representation similarity or probe accuracy?
7. Under what conditions does an O(N) communication hub have lower total risk than O(N^2) pairwise interfaces once hub failure and attack conductivity are included?
8. How should selection quality be measured without relying on the same model family that generated the candidate answers?

## Resolution policy

An open problem is not considered solved from a single positive result. Prefer convergent evidence, independent replication, clear baselines, and explicit consideration of failure modes.
