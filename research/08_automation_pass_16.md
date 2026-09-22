# Cognitive Holobiont — Automation Pass 16

**Date:** 2026-09-23

## Scope
Fresh literature pass focused on distributed coordination, information acquisition, interaction-induced convergence, graph interventions, and governance/security. The originating PDF remains a hypothesis/specification, not evidence.

## New evidence
1. **SILO-BENCH (ACL 2026)** strengthens the central negative result: agents can communicate actively and acquire sufficient information yet fail at integration; performance collapses on high-complexity distributed tasks as scale grows. This keeps distributed computation—not communication—as the decisive unresolved capability.
2. **Interaction Tax (ICML 2026)** gives a stronger causal-looking account of why interaction can hurt: full-solution sharing rapidly collapses proposal diversity under matched budgets. Independent proposals can preserve search coverage. This supports preserving epistemic independence until integration is necessary.
3. **OpenMAS-GCom (Sep 2026)** introduces controlled graph interventions for graph-enhanced MAS. This is important methodologically: topology claims should be tested by intervention, not correlation. The Holobiont evaluation should include edge deletion/addition, relay removal, bottleneck rewiring, and random topology controls.
4. **AgentLeak v3** shows that multi-agent systems can reduce some final-output leakage while increasing total exposure through internal channels. Communication therefore creates a governance surface, not merely a bandwidth cost.
5. **Constraint Drift / MasDrift** strengthen the case that authorization and safety state must survive delegation and communication. Centralized hierarchies can outperform peer networks on both completion and authorization preservation in the reported benchmark.
6. **SCHEME** provides an important adversarial counterexample: multi-agent coordination can be used for coordinated sabotage, and communication visibility materially changes detectability. Any Holobiont claim about resilience must therefore include adversarial/collusive agents, not only benign failures.

## Revised interpretation
The strongest current hypothesis is not “more communication creates collective intelligence.” It is:

> A heterogeneous system may gain genuine distributed-computation capability only when it selectively acquires conditionally useful private information while preserving enough epistemic independence, and when integration is governed by explicit provenance, authorization, verification, and topology controls.

## New research priority
The next decisive benchmark should combine **private-information partitioning + graph interventions + sender ablation + topology perturbation + adversarial/noisy agents + matched centralized/MoE/MAS baselines**. The primary outcome should be conditional coalition synergy, not raw accuracy.

## Status
No implementation is justified yet. Evidence supports narrowing the hypothesis and strengthening the falsification protocol, not claiming validation.
