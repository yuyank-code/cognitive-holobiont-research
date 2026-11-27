# Contradictions, Negative Results and Open Problems — Pass 42

## Contradictions and negative results

1. **Endpoint success can hide unsafe paths.** TraceProbe shows that final-state or final-answer checks can miss unsafe intermediate actions.
2. **More governance is not free.** Policy Algebra raises unsafe-event intervention and audit completeness, but increases false interventions and gate latency and reduces task completion by 3.8 percentage points on its reported workload.
3. **Delegation can amplify authority or budget unless explicitly constrained.** Per-edge budget narrowing is insufficient when concurrent children can reserve the same parent budget; atomic reservation is required.
4. **A stronger model is not uniformly more fault tolerant.** MAS-FIRE reports architecture-dependent robustness and vulnerability to prompt-level corruption under strict instruction following.
5. **Closed-loop critique helps selected faults, not all faults.** Semantic ambiguity and instruction corruption can survive structural/rule filters.
6. **Trace localization can be misleading.** AgentTrace's position features dominate on synthetic single-root traces; real failures can have multiple causes and incomplete logs.
7. **Component health does not imply compound-system health.** The compound reliability preprint identifies failures at retrieval/generation/tool/orchestration/integration boundaries.
8. **Reported MTTR gains can depend on weak baselines.** Compound AI System Reliability compares against unstructured monitoring and explicitly lacks retry-with-backoff as a baseline.
9. **Tool timeout does not mean the remote action failed.** Blind retries can duplicate side effects when the first dispatch partially succeeded.
10. **A fail-closed system can be safe but useless.** Availability, safe completion, useful degraded completion and false quarantine must be measured separately.

## Open questions

- What task contracts can be machine-checked without pretending that semantic quality is fully decidable?
- Which tasks permit useful partial completion, and which must stop when an organ or verifier is unavailable?
- How should the mode selector distinguish unavailable evidence from merely low-confidence evidence?
- Can a local action gateway enforce policy when Heart, Amygdala, provenance journal or network connectivity fails?
- How should a distributed policy root be replicated without creating a new common-mode compromise?
- How should child budgets be reserved atomically under concurrent delegation and retries?
- How can trace contracts capture latent payload ancestry, memory summaries and external side effects?
- How can causal root-cause localization handle multiple interacting faults, missing logs and adversarially manipulated telemetry?
- Which quality gates detect silent semantic drift without unacceptable false intervention?
- What is the correct fallback when a specialist is unavailable but the remaining organs do not possess the required evidence?
- How should an action be reconciled when a timeout occurs after dispatch but before the result becomes visible?
- Can a task-conditioned degradation policy preserve specialist diversity and not simply route every fault to one overloaded generalist?
- How should availability be reported when the service is reachable but safe task completion is impossible?

## Required caveats

- TraceProbe is peer-reviewed EMNLP 2026; its 155 executable scenarios do not represent all deployment environments.
- Policy Algebra is an arXiv preprint; its formal guarantees are conditional on represented policies/context and enforcement assumptions. The finite workload results are descriptive.
- MAS-FIRE is treated as an arXiv preprint because its visible conference/DOI metadata is incomplete.
- AgentTrace uses synthetic single-root scenarios and assumes accurate logs.
- Compound AI System Reliability is an arXiv preprint; its MTTR baseline is unstructured monitoring, and the authors explicitly identify retry-with-backoff as a missing stronger baseline.
- OpsAgent was inspected at abstract/metadata level only because the IEEE full-text page could not be retrieved.
- Verified Tool Calls is a controlled simulation preprint, not proof of exactly-once semantics for arbitrary external APIs.
- Trace-Based Assurance is an arXiv preprint; no independent replication was identified in this pass.
