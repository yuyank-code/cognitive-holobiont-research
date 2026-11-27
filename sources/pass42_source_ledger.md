# Source Ledger — Pass 42

All sources were checked on 2026-11-27. Peer-reviewed status is stated separately from preprint status.

| Source | Status | Contribution to Pass 42 | Important limitation |
|---|---|---|---|
| He et al., TraceProbe, EMNLP 2026 | Peer-reviewed conference paper | 155 executable safety scenarios; trace-level violations; unsafe intermediate actions despite safe endpoints | Benchmark coverage is bounded |
| Tripathi et al., A Policy Algebra for Trust-Preserving Agentic AI Execution, arXiv:2608.16402 | Preprint | Monotone policy composition, delegation narrowing, budget conservation, audit and intervention trade-offs | Formal claims conditional on represented context and enforcement; finite workload |
| Jia et al., MAS-FIRE, arXiv:2602.19843 | Preprint; conference metadata incomplete | 15-fault taxonomy; closed-loop vs linear workflow behavior | Three architectures and bounded benchmarks |
| Wang, AgentTrace, arXiv:2603.14688 | Preprint | Causal dependency graph and backward root-cause localization | 550 synthetic single-root scenarios; accurate logs assumed |
| Paul & Nandy, Compound AI System Reliability, arXiv:2610.02503 | Preprint | 150 incident reports, 23 failure modes, circuit breaker/quality gate/isolation patterns | Naive MTTR baseline; small enterprise sample; stronger retry baseline absent |
| OpsAgent, IEEE ICAISET 2026, DOI 10.1109/ICAISET66439.2026.11541300 | Peer-reviewed conference publication; abstract inspected | Governance-aware operational reliability, MTTR/availability/policy compliance metrics | IEEE full text unavailable in this pass; abstract-only review |
| Mansoor et al., Verified Tool Calls Improve LLM Agent Reliability Under Non-Atomic Failures, arXiv:2608.02645 | Preprint | Postcondition checks, verify-before-retry, idempotency keys | Controlled simulation; no universal exactly-once guarantee |
| Paduraru et al., A Trace-Based Assurance Framework for Agentic AI Orchestration, arXiv:2603.18096 | Preprint | Message-action trace contracts, deterministic replay, bounded counterexample search and action mediation | No independent replication identified in this pass |

## Direct links

- https://aclanthology.org/2026.emnlp-main.1233/
- https://arxiv.org/abs/2608.16402
- https://arxiv.org/abs/2602.19843
- https://arxiv.org/abs/2603.14688
- https://arxiv.org/abs/2610.02503
- https://doi.org/10.1109/ICAISET66439.2026.11541300
- https://arxiv.org/abs/2608.02645
- https://arxiv.org/abs/2603.18096
