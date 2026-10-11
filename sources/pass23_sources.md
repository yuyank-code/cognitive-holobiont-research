# Pass 23 Source Ledger — 2026-10-12

All sources are freely accessible. Venue status is noted to avoid treating preprints as peer-reviewed results.

1. Zhang et al. (2026), **SILO-BENCH: A Scalable Environment for Evaluating Distributed Coordination in Multi-Agent LLM Systems**. ACL 2026 peer-reviewed long paper. https://aclanthology.org/2026.acl-long.1354/ (PDF: https://aclanthology.org/2026.acl-long.1354.pdf; code: https://github.com/jwyjohn/acl26-silo-bench)
2. Shu et al. (2026), **AgentWorld: Benchmarking Long-Horizon Collaboration of Multi-agent LLMs**. Public arXiv version; page states accepted at COLM 2026. https://arxiv.org/abs/2609.31590 (project: https://agentworld.io)
3. YS et al. (2026), **SOTOPIA-TOM: Evaluating Information Management in Multi-Agent Interaction with Theory of Mind**. Public arXiv preprint. https://arxiv.org/abs/2605.02307 (SOTOPIA codebase: https://github.com/sotopia-lab/sotopia)
4. Margalit et al. (2026), **Governed Shared Memory for Multi-Agent LLM Systems**. Public arXiv preprint with production-service evaluation. https://arxiv.org/abs/2606.24535
5. Wang et al. (2025), **Unveiling Privacy Risks in LLM Agent Memory**. ACL 2025 peer-reviewed long paper. https://aclanthology.org/2025.acl-long.1227/ (PDF: https://aclanthology.org/2025.acl-long.1227.pdf)
6. Liu (2026), **Memory Contagion: Cross-Temporal Propagation of Evaluator Bias via Agent Memory**. Public arXiv preprint. https://arxiv.org/abs/2606.23195
7. Nakamura et al. (2026), **Colosseum: Auditing Collusion in Cooperative Multi-Agent Systems**. Public arXiv preprint/audit framework. https://arxiv.org/abs/2602.15198
8. Tran & Kiela (2026), **Single-Agent LLMs Outperform Multi-Agent Systems on Multi-Hop Reasoning Under Equal Thinking Token Budgets**. Public arXiv preprint; negative control against unbudgeted architecture claims. https://arxiv.org/abs/2604.02460

## Citation-chain notes

- SILO-BENCH → AgentWorld: exact-answer distributed computation expands to longer-horizon plans, asymmetric roles, and resource sharing.
- Hidden-profile coordination → SOTOPIA-TOM: information seeking is augmented with recipient/channel-specific privacy constraints.
- Governed shared memory → ACL 2025 MEXTRA: memory lifecycle design is connected to a demonstrated extraction attack surface.
- Memory Contagion → memory governance: lineage and access control are insufficient if biased source experiences are stored as trusted precedent.
- AgentWorld/CCE → Colosseum: graph attribution must be distinguished from realized action outcomes and intervention-based causal validation.
- Equal-token single-agent comparison → all synergy claims: require explicit resource accounting and a best-feasible single-agent baseline.

Reported numerical results remain task/protocol-specific. This pass did not perform a cross-paper meta-analysis.