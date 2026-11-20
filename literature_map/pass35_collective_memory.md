# Living Literature Map — Pass 35: Collective Memory and State Governance

## Project components and evidence clusters

### Distributed memory and continuity
- UMA (EMNLP 2026): proactive structured memory maintenance and one-to-many future QA; a strong single-agent baseline.
- AMA-Bench / AMA-Agent (ICML 2026): long-horizon agent trajectories and causal/objective memory; similarity retrieval alone is insufficient.
- TRACE (arXiv, Sep 2026): temporal admission when an agent returns to an evolving team; actor/metric/subset-dependent, not uniformly best across all its own benchmark tables.
- From Private Experience to Collective State (preprint survey, Sep 2026): OTGE lifecycle taxonomy and quantitative map of formation/maintenance gaps.

### Collective state, provenance and authority
- PPMF (arXiv, Jul 2026): source-authority non-amplification through lossy memory consolidation.
- MemTX (arXiv, Jul 2026): governed record lifecycle, transactional belief commit, action gate and typed cascade repair.
- MAPLE-Guard (arXiv v2, Oct 2026): memory lifecycle gates and cross-agent memory-link propagation.
- ICML 2026 concurrency-control position paper: explicit isolation and conflict detection for shared agent state.

### Memory poisoning and collective false belief
- MemoryDojo (arXiv, Nov 2026): poisoning persistence and later behavioral reach across five memory systems.
- MANBENCH (ICLR 2026): socially reinforced false memory across multi-agent protocols.
- MAPLE-Guard and PPMF: lifecycle/authority controls, with metadata assumptions.
- MemTX: commit, permissions and typed retraction, with lineage and transaction-scope limitations.

### Temporal validity, versioning and re-entry
- TRACE: current admissibility is distinct from retrieval relevance and historical truth.
- UMA: proactive state maintenance as a complement to raw-context retrieval.
- AMA-Agent: causal graph state rather than similarity-only recall.
- MemTX: validity intervals, transaction time and conflict/commit handling.

### Revocation and recovery
- Survey reports only 12/89 papers address revocation and 6/89 address recovery.
- MemTX: typed cascade repair but only along recorded lineage; external effects are logged/compensated rather than replayed.
- TRACE: rejects stale state at re-entry but is not a general poisoning repair system.
- MAPLE-Guard: blocks risky memory lifecycle paths but does not reconstruct all corrupted memories or decisions.
- MemoryDojo: measures poisoning lifecycle and impact; systematic defenses remain future work.

## Status by project claim

| Claim | Current evidence status |
|---|---|
| Proactive memory maintenance can improve long-horizon state tracking | Supported in bounded single-agent settings |
| Causal/objective memory can outperform similarity-only retrieval on agentic trajectories | Supported by ICML 2026 benchmark, within scope |
| Returning agents need temporal re-admission of memory | Promising preprint evidence |
| Memory writes should be staged and committed before action | Promising protocol-level and controlled LLM evidence |
| Poison can propagate across memory links beyond visible message edges | Supported in multiple preprint benchmark settings |
| Social influence can create collective false memories | Supported in controlled peer-reviewed ICLR 2026 setting |
| Provenance survives summarization by default | Contradicted by provenance-laundering work |
| Revocation and recovery are mature research capabilities | Not supported; sparse corpus coverage and limited closure mechanisms |
| A shared memory plane improves a heterogeneous Holobiont over strong single-agent memory | Open; no matched-budget federation experiment |
| A latent Narrative Thread can serve as the authoritative source of shared identity | Unvalidated |

## Architectural synthesis

The memory layer should be a Collective State Plane orthogonal to the organ graph:
- local specialist memories remain private by default;
- only admitted records become collectively consequential;
- role/task scopes determine who may rely on them;
- memory-link ancestry tracks propagation beyond visible messages;
- bitemporal/versioned state governs current validity;
- transactions separate write from commit;
- action gates require current, authorized and lineage-complete support;
- typed revocation and recovery track state, holders and decisions;
- learned narrative/latent summaries remain projections over auditable source state.

## Next literature expansion

1. Recovery closure and dependent-effect repair at large scale.
2. Semantic transaction protocols under concurrent multi-agent writes.
3. Under-admission and false-forgetting costs.
4. Provenance-preserving latent compression and cross-model memory transfer.
5. Team-level memory utility and audience-aware admission.
6. Privacy/deletion propagation through derived summaries, caches and model updates.
