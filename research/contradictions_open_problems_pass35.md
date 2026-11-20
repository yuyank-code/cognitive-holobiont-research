# Contradictions and Open Problems — Pass 35 (2026-11-20)

## New contradictions and cautions

### 1. Shared access is not collective admissibility
A shared store says who can technically retrieve an item. It does not say who should rely on it, whether it is valid now, or whether it may authorize an action.

### 2. Retrieval relevance is not temporal validity
A memory can be topically relevant, correctly retrieved and faithful to its source, yet stale after a teammate changes the shared state. Return-time admission is a distinct operation.

### 3. Memory write is not belief commit
A tentative observation should not immediately become a shared premise or action-safe fact. A commit protocol needs evidence, authority, scope, conflict resolution and a defined lifecycle.

### 4. Provenance is not truth
A perfectly traced record can still be false. Provenance establishes origin and transformation, not factual correctness. Confidence, source authority and factual support must remain separate fields.

### 5. Confidence is not authority
A model can be highly confident in an untrusted webpage or tool result. A record may be epistemically plausible but not authorized to support a high-impact action.

### 6. A message graph is not a memory-propagation graph
A poisoned record can move through private memory, summaries, shared stores and later retrieval without a visible message edge. The immune system must monitor memory lifecycle events, not just inter-agent messages.

### 7. Consensus can amplify false memory
MANBENCH shows that misleading discussion and consolidation can turn initially correct agents wrong. Repeated copies of one source are correlated evidence, not independent corroboration.

### 8. Revocation is not physical deletion
Deleting one vector or text record does not invalidate copies, summaries, derived beliefs, cached indexes, plans or actions. Revocation requires lineage-aware closure. Historical data may remain for audit but must be ineligible as a current premise.

### 9. Cascading invalidation can overreach
Blindly revoking every descendant can discard conclusions that have independent support. Typed dependency edges and re-evaluation are needed; not every derived record is equally dependent.

### 10. Memory poisoning and ordinary world change are distinct
An honest fact can become stale without an attacker. Security-only defenses will miss normal temporal invalidation. Conversely, a poisoned memory may remain harmful even if it appears current.

### 11. Proactive memory can improve performance but increase risk
UMA supports proactive maintenance in single-agent settings. MemoryDojo shows persistent memory can also propagate malicious instructions. Memory utility must be optimized with lifecycle risk, not in isolation.

### 12. False forgetting can be as harmful as false retention
Hard deletion or stale classification can remove a query-critical historical fact. Preserve history with validity labels and supersession rather than assuming old means useless.

### 13. Transactional protocol correctness is not LLM record correctness
MemTX's bounded state-machine checking verifies the protocol implementation under its modeled assumptions. It does not guarantee that the model supplies correct source, lineage, permission or validity fields.

### 14. Repair closure has at least three layers
A memory can be corrected in the store while remaining in another organ's private memory or in a downstream action plan. State closure, holder closure and decision closure must be reported separately.

### 15. Collective identity cannot be inferred from a shared narrative summary
A Narrative Thread may help continuity, but a compact learned state is not proof of persistent identity. It may omit conflicts, source lineage and invalidation dependencies.

## Open questions

1. What exactly makes an item part of collective state: cross-agent access, actual reliance, a downstream decision, or some combination?
2. Can the team measure collective-utility recall—memories that would have helped a receiving organ but were never admitted?
3. How should admission differ for an organ's private analysis versus a memory that can authorize an external action?
4. Can provenance survive compression, paraphrase, translation and latent-space bridges without allowing authority laundering?
5. How should confidence, source authority, permission and factual verification be represented separately?
6. What consistency model is appropriate for long-running agents with asynchronous writes and long inference windows?
7. Can semantic conflict resolution be reliable when two records are not literal opposites but describe different times, roles or contexts?
8. How should bitemporal validity (when a fact held in the world vs when the system learned it) interact with event ordering and transaction commits?
9. How can an organ rejoin after a long absence without either restoring stale memory or discarding useful history?
10. Can revocation find every affected holder, derived summary, retrieval index, plan and action when some derivation edges are missing?
11. When should an invalidated descendant be quarantined, recomputed, retained as history, or permanently deleted?
12. What is the false-revocation rate and how should the system preserve independently supported conclusions?
13. Can memory poisoning be detected when the attacker controls one or more agents but not the platform metadata?
14. How does the system handle forged provenance metadata, compromised event logs or compromised authorization roots?
15. Can memory governance remain safe when the verifier itself is wrong or shares a model family with the organ being checked?
16. Does a shared collective-state plane improve over local per-agent memory plus targeted handoff at matched cost?
17. What is the latency and storage overhead of transaction commits, provenance lineage, event history and cascade repair at realistic scale?
18. How can a Narrative Thread retain useful continuity without becoming a lossy, untraceable authority source?
19. Does the collective memory improve the whole team, or merely the producer that wrote the record?
20. Can the system recover not only memory state but the decisions and external side effects that depended on a revoked belief?

## Revised architecture stance

- Keep local specialist memory and collective memory distinct.
- Define collective state by cross-agent consequence, not storage location.
- Introduce explicit admission, scoping, propagation, reconciliation, revision, revocation and recovery operators.
- Give every shared item platform-maintained provenance, authority, scope, time, validity, type, lineage and lifecycle state.
- Separate confidence from authority and both from truth.
- Use a transactional commit boundary for action-relevant beliefs.
- Use bitemporal/versioned records for historical truth and current validity.
- Track a memory-link graph in addition to the communication graph.
- Preserve a durable event history and typed derivation graph; use materialized views and the Narrative Thread as projections.
- Apply revocation and recovery to affected descendants, holders and decisions.
- Avoid blind hard deletion; quarantine, supersede, revalidate and retain audit history where appropriate.
- Evaluate false admission, under-admission, false revocation, privacy leakage and recovery cost together.
