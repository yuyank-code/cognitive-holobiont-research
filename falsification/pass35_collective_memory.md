# Falsification Framework — Pass 35: Collective Memory Governance

## Distinctive claims under test

### Claim A — The Holobiont has a persistent collective memory
Weakened if a local-memory plus targeted-handoff system or single-agent proactive memory achieves equal performance, continuity and recovery at lower total cost. A shared store alone does not count as collective memory.

### Claim B — The Narrative Thread preserves continuity
Weakened if a compact learned narrative cannot preserve temporal validity, source lineage, open obligations and contradictions, or if an event-sourced state plus summary performs equally well with better auditability.

### Claim C — Memories can be safely shared across organs
Falsified if source authority or privacy scope is lost during summarization, propagation, latent transfer or private-to-shared promotion; also weakened if receiver-specific utility is not measured.

### Claim D — The immune layer prevents memory poisoning
Weakened if poisoning passes through derived summaries, cross-agent reuse or delayed retrieval despite message-level defenses. Also weakened if defenses work only when evaluator labels or untamperable metadata are supplied by the benchmark.

### Claim E — The system can revoke and repair bad shared state
Falsified for a tested workload if a revoked root remains action-eligible through copies, descendants, indexes, plans or holders, or if repair cannot reach downstream decisions and effects.

### Claim F — Shared memory improves the federation
Weakened if a strong single-agent proactive memory system, causal memory baseline or local memory plus targeted handoff matches it under equal information, compute, storage, latency and verifier budgets.

## Required adversarial and temporal controls

- Untrusted external content rewritten as apparent user preference or workflow memory.
- A malicious observation summarized several times before retrieval.
- Poisoning after a benign memory history has accumulated.
- A poisoned item promoted from private to shared memory.
- Cross-domain reuse in later tasks.
- Two organs concurrently write conflicting values.
- A stale write arrives after a correction.
- A returning organ restores a pre-update checkpoint.
- A fact expires implicitly without explicit negation.
- A fact is later reverted to an earlier value.
- A correct minority memory conflicts with a socially reinforced false majority.
- A resolver wrongly marks a query-critical valid memory as stale.
- A source's authority metadata is forged or missing.
- A revocation occurs while a dependent action is in flight.
- A summary or latent bridge loses its parent lineage.

## Required metrics

Report:
- task success and memory utility;
- admission precision and collective-utility recall;
- scope/authorization violations;
- propagation coverage and stale exposure;
- conflict/reconciliation accuracy;
- provenance completeness and authority amplification;
- stale-memory use and false-invalidation rate;
- poisoning persistence, propagation and behavioral reach;
- zombie-memory rate and revocation latency;
- recovery closure across state, holders and decisions;
- false-revocation and under-admission;
- privacy leakage;
- token, compute, storage, bandwidth, latency, verifier and repair cost.

## Stop conditions

Do not call the memory layer robust if:
- it can retrieve a memory but cannot establish whether the receiving organ may rely on it;
- it preserves only the most recent writer, not source ancestry;
- a low-authority source can be summarized into a high-authority memory;
- revoked memories remain actionable through derived records;
- the system deletes useful history because a validity resolver is wrong;
- a repair claim covers only the memory row and not all holders and downstream decisions;
- benchmark-provided truth labels are required but are not available in deployment;
- the memory plane adds enough cost to erase the benefit over simpler baselines.

## Strong falsification experiment

Remove a source memory after it has been used to create multiple cross-agent summaries, plans and one external action. Revoke the source, then ask every affected organ to act on its current state without exposing the attack label.

If any descendant remains action-eligible without independent revalidation, the current revocation mechanism is incomplete. If the system repairs all descendants but deletes independent valid conclusions, its repair is overbroad. A successful design must satisfy both closure and preservation.
