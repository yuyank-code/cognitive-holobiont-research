# Claim–Evidence Matrix — Pass 42 Addendum

| Holobiont claim | New evidence | Status after Pass 42 | Boundary / missing proof |
|---|---|---|---|
| A correct final answer is enough to establish reliable operation | TraceProbe (EMNLP 2026) | Rejected | Endpoint-safe runs can contain unsafe intermediate actions; evaluate the trajectory |
| Delegated organs should inherit the caller's constraints | Policy Algebra preprint | Formalized in a bounded model | Depends on correct policy/context representation and atomic enforcement |
| Parallel delegation must not multiply the parent's budget | Policy Algebra preprint | Strong design rule | Requires atomic reservations under concurrent branching |
| Closed-loop workflows can absorb some faults better than linear pipelines | MAS-FIRE preprint | Supported in tested architectures | Fifteen fault types, three systems; not a universal topology law |
| Root causes can be localized from execution traces | AgentTrace preprint | Promising under complete logs | Synthetic single-root scenarios; multiple causes and missing logs remain open |
| Component health checks detect compound-system degradation | Compound AI Reliability preprint | Insufficient alone | Boundary-level semantic failures can evade component metrics |
| Circuit breakers and isolation reduce fault cascades | Compound AI Reliability preprint | Promising, preliminary | MTTR baseline is weak; standard retry/backoff comparison absent |
| Tool retries are safe after timeouts | Verified Tool Calls preprint | Rejected as a default assumption | Non-atomic actions require postcondition verification and idempotency cooperation |
| Runtime governance can preserve useful capability | Policy Algebra preprint; OpsAgent IEEE 2026 abstract | Partial | Increased false interventions/latency and lower task completion; workload-specific |
| The complete Holobiont can gracefully degrade and remain safe | Combined evidence | Unproven | No end-to-end heterogeneous persistent federation has validated the full mode-selection and recovery contract |

## New sources

1. He et al., TraceProbe, EMNLP 2026: https://aclanthology.org/2026.emnlp-main.1233/
2. Tripathi et al., A Policy Algebra for Trust-Preserving Agentic AI Execution, arXiv:2608.16402: https://arxiv.org/abs/2608.16402
3. Jia et al., MAS-FIRE, arXiv:2602.19843: https://arxiv.org/abs/2602.19843
4. Wang, AgentTrace, arXiv:2603.14688: https://arxiv.org/abs/2603.14688
5. Paul & Nandy, Compound AI System Reliability, arXiv:2610.02503: https://arxiv.org/abs/2610.02503
6. OpsAgent, IEEE ICAISET 2026, DOI: https://doi.org/10.1109/ICAISET66439.2026.11541300
7. Mansoor et al., Verified Tool Calls, arXiv:2608.02645: https://arxiv.org/abs/2608.02645
8. Paduraru et al., Trace-Based Assurance Framework, arXiv:2603.18096: https://arxiv.org/abs/2603.18096
