# Cognitive Holobiont Research — Pass 18 (2026-09-25)

## Scope

This pass preserves the originating PDF as a hypothesis/specification and revisits the current synthesis against recent freely accessible evidence. The emphasis was on whether the program's strongest remaining hypothesis—causal positive coalition synergy from complementary private information—can be separated from better orchestration, shared context, extra compute, or generic coordination effects.

## Executive finding

The evidence now supports a sharper distinction between **collective coordination**, **collective computation**, and **collective emergence**.

1. MAS-BENCH/CAMOC and DeLM strengthen the case that protocol structure and verified shared state can repair important coordination failures.
2. Consilience strengthens the case that communication should be an epistemic control action rather than a fixed exchange schedule.
3. Riedl's PID/TDMI framework provides a promising measurement language for synergy, but its task setting is not yet an exact distributed-computation demonstration.
4. PARSE/PID-guided decentralized federated learning provides a useful adjacent result: decomposing representations into unique, redundant, and synergistic information can improve heterogeneous decentralized collaboration. This is supporting evidence for the mathematical decomposition, not evidence for LLM cognitive synergy.
5. Representational/diversity-collapse results remain a strong warning: interaction can reduce the independence that makes a coalition valuable.

The major revision is therefore methodological: **positive coalition synergy should be defined operationally as a causal, task-relevant performance gain that survives information-, compute-, bandwidth-, verifier-, and redundancy-matched controls and disappears under removal/randomization of the complementary private information.**

## New literature map

### A. Distributed computation / coordination

MAS-BENCH is now peer-reviewed Findings of ACL 2026. It isolates distributed sorting under explicit communication constraints and reports sharp scaling failures in shared state, conventions, and termination. CAMOC improves coordination through collaboration-aware sharing, early metadata, and single-commit verification. This is a strong positive counterexample to the claim that coordination failure is unavoidable, but not a general proof of Holobiont synergy. citeturn1search0

### B. Certified communication control

Consilience is the strongest new evidence for the governed-epistemic-scheduler line. It represents uncertainty, disagreement, evidence gain, redundancy, and premature consensus, then chooses among challenge, clarify, seek-evidence, and routing actions. Its conformal guarantee is a one-step calibrated action-regret guarantee, not a global optimality theorem. The key result for this program is that adaptive communication control can sometimes beat indiscriminate information availability. citeturn1academia48

### C. Verified shared context

DeLM demonstrates that asynchronous agents can coordinate through a shared verified context and task queue, reducing reliance on a central orchestrator and reporting gains on SWE-bench Verified and LongBench-v2. This is now a first-class competitor to private selective routing. citeturn1academia49

### D. Information-theoretic emergence

Riedl's 2026 version of Emergent Coordination uses partial information decomposition of time-delayed mutual information to distinguish redundancy, unique information, and synergy and reports goal-directed complementarity under persona/perspective-taking interventions. The result is valuable as a measurement framework, but the underlying guessing-game setting and minimal feedback do not establish exact distributed computation. citeturn1academia51

### E. Heterogeneous decentralized information decomposition

PARSE applies partial-information decomposition to multimodal decentralized federated learning, explicitly separating latent information into unique, redundant, and synergistic slices and sharing only semantically compatible branches. It provides adjacent support for treating information ownership and synergy as measurable objects in heterogeneous decentralized systems. Transfer to LLM reasoning is an open question. citeturn1academia50

### F. Negative pressure: diversity collapse

Recent committee and open-ended MAS studies continue to find high representational similarity and diversity collapse, with dense interaction accelerating premature convergence. This remains a strong reason not to optimize communication volume or consensus as primary objectives. citeturn0academia0turn0academia1

## Revised central distinction

The program should maintain three separate claims:

- **Coordination claim:** protocols can make agents cooperate reliably.
- **Computation claim:** agents can jointly compute a target that cannot be reliably computed by any matched single system with the same total resources.
- **Holobiont claim:** complementary private information plus adaptive, governed integration yields causal positive coalition synergy and useful resilience.

Current evidence supports parts of the first claim, provides measurement tools for the second, and does not yet establish the third.

## Updated architecture conclusion

Current candidate architecture:

**heterogeneous private specialists → epistemic-state estimator → adaptive action scheduler → choice of private routing / verified shared context → sparse topology → causal communication interface → provenance + authorization + privacy → dependency-aware integration → independent verification → termination → governed memory → bounded repair → validation-gated reconfiguration**

The scheduler should be allowed to choose *not* to communicate, to challenge a consensus, or to preserve an independent hypothesis.

## Updated falsification target

The decisive benchmark should combine:
- hidden-profile tasks with deliberately partitioned private evidence;
- exact distributed-computation tasks;
- topology interventions;
- sender ablation and ownership permutation;
- broadcast vs fixed schedule vs adaptive scheduler vs verified shared context vs hybrid;
- matched total inference compute;
- matched evidence access;
- matched communication budget;
- matched verifier calls;
- adversarial/noisy agents;
- pre/post communication diversity measurement.

A strong Holobiont result requires positive causal synergy under these controls, not merely higher raw benchmark accuracy.

## Bottom line

The program is converging on a testable scientific object: **causal information synergy under governed, resource-matched distributed computation**. The evidence for the control layer is now substantially stronger than the evidence for the cognitive-synergy layer. No implementation conclusion is justified yet.
