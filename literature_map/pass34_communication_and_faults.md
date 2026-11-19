# Living Literature Map — Pass 34: Communication Fabric and Fault Resilience

## Project components and evidence clusters

### Connective tissue and communication correctness
- When Messages Go Wrong (arXiv, Oct 2026): semantic and partial-content faults, silent failures, alternative evidence paths.
- Routed Graph Handoff (Findings EMNLP 2026): adaptive choice between typed dependency graphs and natural language.
- RCR-Router (Findings EMNLP 2026): selective role/task-stage/token-budget routing of shared memory.

### Dynamic routing and resource allocation
- RouterHGC (Findings ACL 2026): graph-conditioned selection of roles, models and collaboration modes.
- GoAgent (arXiv, Mar 2026): group-of-agents topology generation and conditional information bottleneck; retained as a related candidate, not the principal new evidence in Pass 34.
- Earlier competence-aware orchestration work: task-conditioned collaboration as a way to avoid paying coordination overhead on easy tasks; requires matched-budget replication.

### Fault injection and reliability engineering
- AgentChaos (ASE 2026): runtime injection of API crash, omission and value faults.
- MAS-FIRE (arXiv, Feb 2026; indexed in Pass 33): semantic and coordination fault injection.
- When Messages Go Wrong (arXiv, Oct 2026): communication-stage faults and evidence-path recovery.

### Causal repair and recovery
- Repair or Resample (arXiv, Aug 2026): deterministic trace anchors, failure reproduction, symptom-driven intervention.
- Pass 33 sources: localized neural repair, hypernetwork repair modules, and recoverability-gated self-modification. These remain separate from trajectory-level MAS repair.

## Status by project claim

| Claim | Current evidence status |
|---|---|
| Selective sharing can reduce communication cost | Supported in bounded peer-reviewed benchmarks |
| Hybrid structured/natural-language handoff can outperform a fixed format | Supported in bounded peer-reviewed benchmarks |
| Task-conditioned role/agent routing can improve cost/quality | Supported in bounded benchmark settings |
| Alternative paths can preserve evidence after downstream communication failure | Supported conditionally in one large preprint study |
| Semantic and partial-content failures can be silent | Supported by two complementary fault-injection lines; one is a recent preprint |
| Trace-anchored diagnosis is better than unguided reruns | Promising preprint evidence; more replication needed |
| Latent bridges are superior to selective structured/hybrid communication | Open; not tested by the Pass 34 sources |
| Holobiont-specific emergent synergy | Open; requires matched-budget causal intervention |
| Full organ regeneration from surviving organs | Still unproven; not addressed by these communication studies |

## Research direction

The next literature expansion should focus on:
1. source lineage and information-theoretic redundancy in distributed systems;
2. semantic checksums and end-to-end evidence contracts for LLM communication;
3. adaptive routing under correlated model and retrieval failures;
4. causal replay and repair in long-horizon agent workflows;
5. empirical comparisons between latent bridges and structured/hybrid protocols.
