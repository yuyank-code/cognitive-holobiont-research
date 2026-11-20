# Experiment Backlog — Pass 35: Collective Memory and Lifecycle Governance

## E35-A — Collective-state lifecycle microbenchmark

**Question:** Can a small organ network manage the full lifecycle of a memory item rather than merely store and retrieve it?

Use three organs: producer, consumer and auditor. Create a controlled set of observations, derived summaries, plans and actions. Exercise admission, scoping, propagation, reconciliation, revision, revocation and recovery.

Compare:
- local-only memories;
- naive shared store;
- shared store plus metadata;
- event-sourced/versioned state;
- OTGE-style operator layer;
- transactional belief commit.

Measure task utility, unauthorized reliance, stale use, false admission, under-admission, provenance completeness, revocation and recovery closure, and cost.

## E35-B — Return after state change

An organ leaves with a valid checkpoint. The remaining organs change shared facts, supersede an earlier plan, and leave open obligations. The original organ returns.

Compare:
- full checkpoint restore;
- reset/no memory;
- static shared memory;
- timestamp-only freshness;
- event-sourced reconstruction;
- TRACE-like return-time admission;
- write-time consolidation.

Vary absence duration, number of updates, implicit versus explicit invalidation, and role changes. Measure valid-information availability, invalid-information rejection, obligation coverage, token cost and false abstention.

## E35-C — Cross-agent memory poisoning

Inject malicious or misleading content through an ordinary document, email, webpage or tool result. Allow the producer organ to summarize it, store it, promote it to shared memory and expose it to a different organ in a later session.

Compare:
- no defense;
- write-only filter;
- retrieval-only filter;
- write + retrieval + promotion + cross-agent lifecycle gates;
- authority/provenance gate;
- transaction/commit gate;
- combined lifecycle governance.

Track insertion, persistence, propagation, retrieval, behavioral reach, benign-memory utility, and downstream action harm. Use multiple memory backends and memory-aware adaptive payloads.

## E35-D — Provenance laundering through summaries and latent bridges

Start with a low-authority external observation. Rephrase it into a benign-looking summary, profile, workflow note, shared memory and latent summary. Test whether each transformation preserves source authority and lineage.

Compare:
- text-only summary;
- typed structured record;
- signed/immutable platform metadata;
- latent bridge plus sidecar provenance;
- latent-only transfer.

A latent-only channel should fail the action-admission test if it cannot preserve or bind the source lineage and scope. Measure authority amplification, metadata loss and unauthorized high-risk actions.

## E35-E — Concurrent writes and belief commits

Two or more organs write updates to the same entity/attribute while one has stale state. Include:
- stale late writes;
- dirty reads of tentative beliefs;
- semantic conflicts;
- out-of-order event arrival;
- private-to-shared permission laundering;
- retry after transaction abort;
- concurrent revocation and update.

Compare last-write-wins, snapshot isolation, serializable/optimistic commit, semantic reconciliation and MemTX-style lifecycle states. Measure dirty reads, lost updates, stale commits, action safety, legitimate-action availability and cost.

## E35-F — Revocation and recovery closure

Seed a root memory, then create:
- a derived belief;
- a compressed summary;
- a private copy in another organ;
- a shared index/cache entry;
- a plan;
- an external tool action.

Revoke the root. Compare row deletion, tombstone-only, dependency-aware quarantine, typed cascade repair and full re-evaluation from independent evidence.

Measure:
- state closure;
- holder closure;
- decision/action closure;
- false revocation of independently supported descendants;
- recovery latency and cost;
- unresolved irreversible harm.

## E35-G — False forgetting and under-admission

Inject resolver errors into validity labels. Include reversion cases where a fact becomes valid again after a later change. Compare hard deletion, soft retention, quarantine, supersession, bitemporal versioning and query-critical revalidation.

Measure false-drop harm and false-keep harm separately. Preserve historical facts where they remain useful for temporal queries.

## E35-H — Collective utility versus producer utility

Let an organ write a memory that helps its own next task but may mislead another organ. Compare admission policies trained or selected on:
- producer-only outcome;
- receiver-specific usefulness;
- team-level utility;
- risk-adjusted team utility.

Use counterfactual task assignment and held-out receiving roles. Measure collective-utility recall, downstream error, privacy leakage and duplicate memory obligations.

## E35-I — Collective false memory and source dependence

Use MANBENCH-style social persuasion and MemoryDojo-style persistent poisoning. Vary:
- shared model family vs heterogeneous models;
- independent sources vs copied descendants;
- agent group size;
- memory consolidation frequency;
- private vs shared scope;
- source scrutiny and provenance checks.

Measure false-memory rate, reality shift, source-lineage diversity, persistence and correction latency.

## Required controls

- Strong single-agent proactive memory (UMA-style) with the same information.
- AMA-Agent-style causal memory baseline.
- Local memory plus targeted handoff.
- Naive shared store.
- Full transcript/RAG.
- Event-sourced current-state view.
- Transactional and lifecycle-governed memory.
- No-memory baseline.
- Matched verifier and information budgets.

## Pass/fail criteria

A collective-memory feature is not accepted merely because retrieval accuracy improves. It must improve one or more of collective utility, temporal validity, provenance, authorized reliance, revocation completeness or recovery closure without unacceptable regressions in task utility, privacy, under-admission, false revocation, latency or total cost.

The most decisive initial sequence is E35-B, E35-C and E35-F. Together they test stale re-entry, persistent poisoning and the system's ability to withdraw and repair collective state.
