# Mathematics Addendum — Pass 35: Collective Memory Governance

## 1. Memory-mediated collective state

Let C be a team of organs and M its persistent memory records. Define:

S_C^M(t) = {m ∈ M : Persistent(m) ∧ MemoryMediated(m) ∧ CrossAgentRelation(m) ∧ CollectivelyConsequential(m)}.

The definition follows the OTGE survey's distinction between persistence, accessibility and governed reliance. A shared cache is not automatically collective state; a private record can become collective state if it is represented in a way that changes another organ's decision.

## 2. Memory object

Represent each record as:

m = (x, s, p, a, scope, t_event, t_record, V, version, lineage, type, confidence, state, privacy)

where:
- x: content, embedding or latent representation;
- s: originating source or observation;
- p: responsible principal/writer;
- a: source authority and permitted operations;
- scope: audience, role, task and purpose;
- t_event: when the described event occurred;
- t_record: when the system recorded/committed it;
- V: validity interval or temporal predicate;
- version: record version;
- lineage: typed derivation graph;
- type: observation, belief, summary, plan, index, action or other governed artifact;
- confidence: epistemic uncertainty;
- state: lifecycle state;
- privacy: disclosure and retention classification.

Do not collapse confidence, source authority and truth into one trust score.

## 3. Action-time admissibility

For organ j, action A and time t, define:

Admit(m,A,j,t) =
Current(m,t)
∧ Authorized(p,A,j)
∧ ScopeAllows(scope,j,A)
∧ ProvenanceComplete(m)
∧ DependenciesAdmissible(m,t)
∧ ConflictResolved(m,t)
∧ EvidenceSufficient(m,A)
∧ LifecycleState(m) = action_safe.

This is a policy predicate, not a proof that m is true. Factual verification remains an independent requirement. Read-only analysis may be permitted at a lower lifecycle state than irreversible action.

## 4. Bitemporal validity

A fact needs at least two temporal coordinates:
- valid time: when the claim holds in the modeled world;
- transaction time: when the system learned, recorded or committed the claim.

A late-arriving write may have an old valid time but a newer transaction time. Last-write-wins by arrival time can therefore restore an obsolete belief. Reconciliation must inspect both axes and the source's authority.

For a record m, define Current(m,t) = 1 only when t lies in its valid interval and no higher-authority, admissible superseding event invalidates it under the task's conflict policy.

## 5. Transactional belief commit

Let a transaction T open against snapshot S_k. It stages tentative writes W_T. A commit operation may publish only a subset W'_T after:
- source/evidence validation;
- permission and scope checks;
- conflict reconciliation against the snapshot and concurrent updates;
- provenance/lineage recording;
- temporal validity assignment;
- action-risk gating.

A transaction protocol can prevent dirty reads and certain stale-write anomalies, but it cannot make an incorrect source true. The LLM's ability to fill record metadata is a separate failure surface.

## 6. Memory-link graph and propagation

Let G_m = (V_m,E_m) be a directed graph of memory items and lifecycle events. Edges represent derivation, summarization, copying, indexing, promotion, retrieval and action support.

This graph differs from the visible organ communication graph G_c. A memory can move between organs through a shared store or retrieval path without a direct message edge.

For each memory item m, record its source ancestry A(m), not merely the most recent writer. Repeated descendants of one source are correlated evidence and must not be counted as independent corroboration.

## 7. Typed revocation closure

Let r be a revoked root item. Define the potentially affected descendant set:

D*(r) = {d : there exists a path r → ... → d and the edge semantics make d dependent on r}.

Each descendant requires a type-specific action:
- belief: revoke or re-evaluate;
- summary/profile: quarantine and rebuild;
- index/cache: invalidate and regenerate;
- shared copy: remove action eligibility at every holder;
- plan: re-evaluate;
- external action: compensate if possible or record unresolved harm.

A descendant with independent admissible support may survive, but only after re-evaluation. Blind deletion is not a valid general cascade algorithm.

## 8. Recovery closure

Report a vector, not a single scalar:

C_recover = (C_state, C_holders, C_decisions)

where:
- C_state: fraction of affected stored state correctly repaired;
- C_holders: fraction of affected organs/replicas no longer relying on invalid state;
- C_decisions: fraction of downstream plans/actions corrected, compensated or explicitly recorded as irreversible harm.

A system is not fully recovered merely because the original memory row is deleted.

## 9. Collective utility

For memory m and audience A(m), define:

U_collective(m) = Σ_{j∈A(m)} π_j [u_j(m) - r_j(m)] - c_store(m) - c_verify(m) - c_disclose(m) - c_repair(m).

Here u_j is utility to receiving organ j, r_j is misapplication risk, and π_j weights the audience/task. This separates producer utility from team utility. The form is a research hypothesis adapted from the OTGE survey, not a proven optimal objective.

## 10. Proposed metrics

- Admission precision = correctly admitted / all admitted.
- Collective-utility recall = beneficial candidate memories admitted / all beneficial candidate memories, with counterfactual task evaluation.
- Unauthorized exposure = retrievals outside permitted audience/purpose / all retrievals.
- Stale reliance rate = actions using expired/superseded memory / actions supported by memory.
- Provenance completeness = records with recoverable source and derivation lineage / records that can affect cross-agent action.
- Zombie-memory rate = revoked or superseded records still action-eligible after the allowed propagation interval.
- Revocation latency = time from revocation event to last affected holder/action path becoming ineligible.
- Recovery closure = report C_state, C_holders and C_decisions separately.
- False-revocation rate = useful valid memories incorrectly made unavailable / all useful valid memories.
- Memory poisoning reach = fraction of later tasks or organs whose behavior is affected by a poisoned memory.
- Under-admission = fraction of counterfactually useful memories not admitted.
- Repair cost = tokens, compute, storage, latency and external-action compensation cost.

## 11. Resource vector

Compare memory architectures under:

B = (C_train, C_infer, M, BW, L, I, V, P, R)

where C_train/infer are compute, M memory, BW bandwidth, L latency, I information access, V verifier budget, P provenance/recording overhead, and R repair/recovery cost.

A federation should not claim memory-governance superiority if it wins only by storing more history, invoking more verifiers, or spending more tokens than its baselines.
