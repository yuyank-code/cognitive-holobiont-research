# Cognitive Holobiont Research — Pass 35
**Date:** 2026-11-20  
**Focus:** Distributed memory as governed collective state: admission, scope, propagation, reconciliation, temporal validity, revocation, recovery, provenance, concurrency and memory poisoning.

## Executive conclusion

This pass investigates the Treatise's Hippocampus, Narrative Thread and shared memory ambitions. The question is not simply how the organs store and retrieve information. It is how an observation created by one organ becomes something another organ is allowed to rely on, how that reliance changes over time, and how the system withdraws and repairs information after it is found to be stale, false, unauthorized or poisoned.

The strongest new conclusion is architectural:

**The Holobiont needs a cross-cutting collective-state governance plane, not merely a shared memory store or one central Hippocampus.**

A shared store provides access. It does not establish that a record is true, current, authorized, safe for a particular role, or suitable as a premise for an external action. The new literature identifies this as a reliance gap and shows that the field is much stronger at creating and retrieving memories than at revoking and repairing them.

A 2026 survey of 89 LLM-agent papers reports:
- admission decisions in 77 papers;
- revision in 52;
- propagation in 36;
- scoping in 25;
- reconciliation in 22;
- revocation in 12;
- recovery in only 6.

This is the central gap for the Holobiont: the architecture imagines persistent collective memory and regeneration, but the research base has far fewer mechanisms and measurements for withdrawing bad shared state and repairing its descendants than for writing or retrieving it.

New empirical work strengthens the case for proactive state maintenance, causal memory, return-time temporal admission, transactional belief commits, and lifecycle-aware poisoning controls. It does not establish a complete distributed autobiographical memory or an emergent persistent identity.

## 1. Project-specific question

The originating Treatise proposes a Hippocampus that preserves episodic experience, a Narrative Thread that keeps organs temporally coordinated, and a bloodstream that exposes compact shared state. These components are meant to make the organs function as one persistent cognitive system.

This pass asks:

1. When does a private observation become collective state that other organs may rely on?
2. Who is authorized to read, revise, promote, or act on a memory?
3. How should the system reconcile conflicting or concurrent updates?
4. How does it distinguish historically true from currently valid?
5. Can a poisoned memory move across agents without a visible communication message?
6. When a source memory is revoked, can all derived memories, holders, plans and actions be found and repaired?
7. How should the system avoid both over-admission and destructive false forgetting?
8. Does proactive memory maintenance improve a multi-agent federation beyond strong single-agent memory and ordinary retrieval baselines?

## 2. New conceptual synthesis: from shared memory to collective state

### 2.1 The reliance gap

**From Private Experience to Collective State: A Survey of Multi-Agent Memory Formation and Maintenance** (Wang et al., 2026; preprint, 62 pages, DOI 10.5281/zenodo.22288996) argues that the usual memory pipeline—representation, storage, retrieval and use—does not capture the governance problem in teams.

It defines memory-mediated collective state by four properties:
- persistence;
- memory mediation;
- a cross-agent relation;
- collective consequence.

This is a useful boundary for the Holobiont. A shared cache that no organ relies on is not necessarily collective memory. Conversely, a private record may become part of collective state when it is summarized, copied, or used as a premise by another organ.

The survey's Object–Transition–Guarantee–Evaluation (OTGE) framework identifies seven operators:

**Formation**
1. Admission: should the item become eligible for collective reuse?
2. Scoping: who may or should rely on it?
3. Propagation: who actually receives or retrieves it?
4. Reconciliation: how should conflicting views be resolved?

**Maintenance**
5. Revision: how does one informational lineage evolve?
6. Revocation: when must agents stop relying on it?
7. Recovery: how are affected state, holders and decisions repaired?

Six guarantees constrain these operators: provenance, attribution, authority, consistency, privacy and confidence. Cost is charged across all operations rather than treated as a separate guarantee.

The survey is a curated preprint, not a controlled experiment. Its counts depend on its inclusion criteria and coding rules. Its value here is the lifecycle taxonomy and evidence-gap map, not proof that one architecture is best.

### 2.2 Why the coverage gap matters

The survey's corpus contains 89 papers: 62 systems, 16 analyses/attacks and 11 benchmarks. It reports 77 papers with admission, 52 with revision, 36 with propagation, 25 with scoping, 22 with reconciliation, 12 with revocation and 6 with recovery.

This is not a small implementation detail. A system that can remember but cannot reliably revoke is vulnerable to zombie memories: facts that remain retrievable and actionable after their validity has ended. A system that can revoke but cannot discover descendants leaves derived summaries, plans and actions contaminated.

The survey also finds that evaluation remains outcome-heavy: task success and retrieval accuracy are much more common than measurements of collective-state properties. It highlights under-measured quantities including collective-utility recall, handoff sufficiency, recovery closure and repair cost.

### 2.3 Revised interpretation of the Treatise

The Hippocampus should remain a specialist memory organ, but it should not be the sole authority for shared memory. The more defensible architecture is:

- local episodic and semantic stores owned by individual organs;
- a cross-cutting collective-state governance plane;
- a versioned event/provenance history;
- task- and role-scoped materialized views;
- transaction and action gates;
- typed dependency tracking for revision, revocation and recovery.

The Narrative Thread should be a compact, learned continuity representation or view, not the only source of truth. If a latent summary cannot preserve or reference provenance, validity, authorization and dependencies, it must not independently authorize high-impact actions.

## 3. New evidence

### 3.1 AMA-Bench — causal and objective memory for agentic trajectories

**Status:** peer-reviewed, ICML 2026, Proceedings of Machine Learning Research 306.  
**Paper:** https://proceedings.mlr.press/v306/zhao26bs.html

AMA-Bench argues that dialogue-centric memory benchmarks miss the state/action/observation/tool-output trajectories that make up real agent work. It introduces long-horizon trajectories and expert-curated questions, alongside synthetic trajectories that can be scaled to arbitrary horizons.

The authors report that current memory systems often miss causal and objective information and rely heavily on lossy similarity retrieval. Their AMA-Agent uses causal-graph construction and tool-augmented retrieval, reporting 57.22% accuracy on AMA-Bench, 11.16 percentage points above the strongest baseline.

**Holobiont relevance:** memory should preserve not just a semantically similar note but the causal and objective relations that explain what happened, what changed, and what remains to be done.

**Boundary:** this is not a multi-organ memory federation. Its headline result does not establish collective memory governance, revocation, privacy or poisoning resistance.

### 3.2 UMA — proactive memory maintenance can beat passive query-time retrieval

**Status:** peer-reviewed, EMNLP 2026.  
**Paper:** https://aclanthology.org/2026.emnlp-main.1299/

Unified Memory Agent (UMA) trains a single policy to maintain a structured memory bank through add, update, delete, retrieve and list operations, then answer multiple future questions using both structured memory and raw-context retrieval. It is trained in a one-to-many setting: one query-agnostic memory state must serve several later QA sessions.

At a 16k context budget, UMA-Generalist achieves the highest aggregate score among compared methods across the paper's test-time-learning and accurate-retrieval benchmarks. It transfers to Ledger-QA without task-specific training; UMA-Specialist improves further after Ledger-QA adaptation.

**Holobiont relevance:** a memory organ may need to maintain state proactively as experience arrives, rather than wait for each later organ to reconstruct it from raw history.

**Boundary:** the paper explicitly studies single-agent settings with a fixed tool interface. Ledger-QA is a controlled synthetic diagnostic; real-world proactive state maintenance, multi-agent writes, evolving APIs and finer attribution of individual memory operations remain open.

### 3.3 TRACE — memory must be re-admitted when an organ returns

**Status:** arXiv preprint, submitted 27 September 2026.  
**Paper:** https://arxiv.org/abs/2609.33517  
**Code:** https://github.com/xiong-wenjun/TRACE

TRACE studies the returning-agent problem. An organ may leave a team with a valid memory, while the other organs update the shared state. When it returns, its old memory may still be relevant and faithfully retrieved but no longer valid for action.

TRACE introduces a return-time admission layer. It reconciles the departure checkpoint with updates made during absence, checks explicit and implicit invalidation, and produces a bounded Return View that covers the returning role's open obligations.

On its derived ManBench-Return setting, the paper reports 92.6–98.3% valid-information availability and 98.4–99.5% invalid-information rejection. In the paper's actor-specific STALE Type II aggregation, TRACE is ahead of the listed comparison methods by 22.3 points for Qwen, 18.5 for Gemini and 27.5 for DeepSeek. However, results are not uniform across every table/benchmark: a separate STALE Type II subset table reports CUPMem at 80.56 overall versus TRACE at 58.89, and the authors state that TRACE does not consistently lead on Memora. The headline advantage is therefore actor-, metric- and subset-dependent, not universal. A write-time consolidation pipeline is reported as more accurate still in one comparison, at about 3.99 times TRACE's token use.

**Holobiont relevance:** an organ's memory cannot be trusted merely because it was valid when the organ went offline. Re-entry is a new authorization and temporal-validity boundary.

**Limitations:** TRACE assumes authenticated return, preserved departure checkpoints and source receipts. Implicit invalidation depends on candidate coverage and verifier calibration. It degrades as absence intervals lengthen and has meaningful token overhead. It does not establish resistance to arbitrary memory poisoning or forged provenance.

### 3.4 MemTX — a memory write is not a belief commit

**Status:** arXiv preprint, under review, submitted 27 July 2026.  
**Paper:** https://arxiv.org/abs/2607.23929  
**Code:** https://github.com/lxy1134/MEMTX

MemTX treats a memory record as a governed object with evidence, permissions, provenance, validity, type and derivation links. Writes are staged in snapshot-isolated transactions and pass a validate-and-commit pipeline. Reads have isolation levels. Irreversible tool calls are gated. Retraction triggers typed cascade repair over the derivation graph.

The paper reports:
- a 90-case main suite across six corruption families and ten domains;
- a 56-case hardened suite with compound corruptions;
- five backbones from three model families;
- bounded exhaustive enumeration of 5,530,160 canonical protocol states and 10,537,260 transitions with zero invariant violations;
- zero downstream harm in its 24-episode downstream pipeline across tested backbones.

**Holobiont relevance:** the memory layer needs transaction semantics and action-time gates. A tentative observation should not immediately become an action-safe shared belief.

**Important limits and negative results:**
- The LLM evaluation path uses only the weak form of the action gate; the strong external-action gate is exercised on the scripted path.
- The strong gate's condition is existential: the snapshot contains at least one action-safe record, not necessarily that the specific inputs to the action are safe.
- Cascade repair only reaches recorded provenance. Unrecorded derivations are invisible.
- Tool compensation is a logged obligation, not environment-level replay; reversibility is a static per-tool designation.
- All methods fail the paper's source-scope cases when an agent paraphrases private content into a shared summary without declaring the parent lineage.
- A stale-write retry can escape a transaction-level staleness check because the fresh retry snapshot already contains the rival write.
- The bounded model check verifies the protocol state machine, not the truth or correctness of the LLM-supplied records.

MemTX is promising protocol engineering, not a proof that an LLM team can maintain true beliefs.

### 3.5 MAPLE-Guard — poisoning travels through memory links, not only messages

**Status:** arXiv preprint, v2 submitted 3 October 2026.  
**Paper:** https://arxiv.org/abs/2608.00426  
**Code:** https://github.com/xiong-wenjun/MAPLE-Guard

MAPLE-Guard models write, retrieval, private-to-shared promotion and cross-agent reuse as memory lifecycle gates. A poisoned record can affect another organ after the visible message that introduced it has disappeared.

In its AppWorld action-selection proxy with Gemma Base, full lifecycle enforcement reports 88.4% multi-agent defense success and 0.1% retrieval-damage ASR, compared with 65.0% and 21.6% for retrieval-only filtering. Its LongMemEval-MemoryGraft ablation finds promotion to be an important propagation point.

**Holobiont relevance:** the memory graph is a second propagation network. The communication graph alone cannot show which organs have inherited a poisoned belief.

**Limitations:** the attacker cannot modify hidden guard metadata or the topology. The method assumes reliable provenance and retrieval traces; forged metadata or payloads below per-event thresholds may evade it. The full-feedback setting uses evaluator-derived outcomes, and the risk scorer includes fixed lexical/metadata heuristics. Attack-free utility is not uniformly improved.

### 3.6 MemoryDojo — poisoning persists across sessions and memory architectures

**Status:** arXiv preprint, submitted 6 November 2026.  
**Paper:** https://arxiv.org/abs/2611.09721

MemoryDojo contains 155 multi-session trajectories across four domains and supports five memory systems: A-MEM, Graphiti, Letta, Mem0 and Memora. It traces insertion, persistence, propagation, retrieval and later behavioral impact.

The authors report that all five memory systems are susceptible, with substantial differences in how poison persists and spreads. A memory-aware poison optimization process increases attack success by approximately 2–31% in the paper's evaluated settings. In a history-prefixed cross-domain condition, later-task reach remains in four of five systems; poison can also degrade recall of benign history in some systems.

**Holobiont relevance:** an organ may inherit a poisoned memory without receiving a malicious message in the current round. Memory ancestry must therefore be tracked across sessions, summaries, promotions and retrievals.

**Boundary:** the benchmark uses sandboxed task suites, synthetic trajectories and locally hosted memory. The paper says data, integrations and evaluation code will be released; this pass does not treat the benchmark as independently reproduced.

### 3.7 MANBENCH — collective memory can become collectively false

**Status:** peer-reviewed, ICLR 2026.  
**Paper:** https://arxiv.org/abs/2602.00428  
**Conference poster:** https://iclr.cc/media/iclr-2026/Slides/10006567_wqA8k4m.pdf

MANBENCH studies the Mandela effect in multi-agent LLM systems using 20 tasks, 4,838 questions, five interaction protocols and 13 LLMs. The paper reports that prompt-level source scrutiny/cognitive anchoring and model-level defenses reduce the measured effect by an average of 74.40% against its baseline.

**Holobiont relevance:** multiple organs can reinforce a false shared memory. A majority of memories is not equivalent to independent corroboration, especially when agents share upstream evidence or social influence.

**Boundary:** the benchmark uses multiple-choice tasks to obtain controlled measurements. The authors note that open-ended discussion, dynamic role changes and real-world team tasks require further study.

### 3.8 PPMF — provenance authority must not be upgraded by summarization

**Status:** arXiv preprint, submitted 31 July 2026.  
**Paper:** https://arxiv.org/abs/2607.29167

The paper identifies memory provenance laundering: an external observation is summarized into something that looks like user history or approved workflow, while the low-authority origin is lost. It proposes a Provenance-Preserving Memory Firewall that keeps authority fields platform-maintained and gates actions according to the authority of their supporting memories.

Its schema-grounded evaluation reports no unauthorized high-risk action passing when provenance, confirmation and risk labels remain intact.

**Holobiont relevance:** learned summaries and latent bridges must not silently convert untrusted content into trusted collective belief.

**Boundary:** this is a preprint and its result depends on intact platform-maintained provenance, confirmation and risk labels. It is not a general guarantee against arbitrary corruption or compromised metadata.

### 3.9 Concurrency control is a memory requirement, not just an orchestration detail

**Status:** peer-reviewed position paper, ICML 2026, PMLR 306.  
**Paper:** https://proceedings.mlr.press/v306/yang26dy.html

The paper argues that concurrent agents can produce stale reads, lost updates and inconsistent outcomes, especially because LLM inference windows are long. It recommends explicit conflict detection, isolation guarantees and structured access to shared resources.

This is a position paper, not a benchmark proving one isolation level is best. It nevertheless makes a strong design case for treating concurrent memory updates as a database-consistency problem rather than hoping prompts will serialize agents.

## 4. Updated architecture hypothesis

The memory subsystem should be a cross-cutting **Collective State Plane**.

### Local memory
Each organ may maintain private episodic traces, specialist knowledge and local working state. Private memory is not automatically eligible for sharing.

### Collective-state records
Every memory that can influence another organ should carry:
- content or representation;
- source and source authority;
- writer/principal and responsible organ;
- audience, scope and purpose;
- event time and record/commit time;
- validity interval and version;
- provenance and typed derivation edges;
- epistemic confidence;
- verification/commit state;
- privacy and permission labels;
- downstream plans/actions that rely on it.

### Lifecycle
A candidate record moves through:
raw observation → tentative → validated → committed → action-safe.

It may also become quarantined, superseded or revoked. These are logical states, not necessarily physical deletion. Historical records may be retained for audit while being denied as premises for current action.

### Seven operators
Implement admission, scoping, propagation, reconciliation, revision, revocation and recovery as explicit operations. They may be composed, but their decisions and costs should be observable.

### Transaction and action boundaries
A write is not a commit. A retrieved record is not automatically action-safe. Concurrent writes should use explicit snapshots/versions and conflict checks. External actions should require current, authorized, lineage-complete supporting beliefs.

### Typed revocation and recovery
When a root item is revoked, follow typed derivation edges. Beliefs, summaries, indexes, private copies, shared copies, plans and tool actions require different repair actions. Do not blindly delete every descendant: independent evidence may preserve some derived conclusions, but those conclusions must be re-evaluated.

### Continuity and narrative thread
The Narrative Thread may summarize the current shared episode, but it should point to versioned source events and obligations. It is a learned view over governed state, not a replacement for provenance or the event history.

## 5. Revised mathematical formalization

Let a memory item be:

m = (x, s, p, a, scope, t_event, t_record, V, version, lineage, type, confidence, state, privacy)

where x is content/representation, s is source, p is the responsible principal, a is authority metadata, V is the validity interval, lineage is the typed derivation graph, and state is the lifecycle state.

For action A by organ j at time t, define an action-admission predicate:

Admit(m,A,j,t) =
Current(m,t)
AND Authorized(p,A,j)
AND ScopeAllows(scope,j,A)
AND ProvenanceComplete(m)
AND DependenciesAdmissible(m,t)
AND ConflictResolved(m,t)
AND EvidenceSufficient(m,A).

Confidence is not authority; authority is not truth. Passing this predicate makes a record eligible to support an action under the declared policy. It does not prove factual correctness.

For a root record r, define its typed affected-descendant closure:

D*(r) = {d : there is a derivation path r → ... → d and the edge semantics make d dependent on r}.

Revocation must re-evaluate every d in D*(r), not merely delete r. Recovery closure should be reported as a vector:

C_recover = (C_state, C_holders, C_decisions)

where the terms measure repair of stored state, all affected agent holders, and downstream plans/actions respectively.

Define collective utility of a memory item:

U_collective(m) = Σ_j π_j [u_j(m) - risk_j(m)] - c_maint(m) - c_disclosure(m)

where π_j weights the relevant audience, u_j is expected utility to organ j, risk_j is misapplication risk, and costs include storage, verification, propagation, privacy exposure and repair.

This formalization is a research proposal synthesized from the Treatise and the new literature, not a validated optimal objective.

## 6. Evaluation framework

Do not use one scalar memory score. Report at least:

- admission precision, harmful-admission rate and collective-utility recall;
- scope correctness and unauthorized exposure;
- propagation coverage, delay and stale exposure;
- reconciliation accuracy and unresolved-conflict rate;
- provenance completeness and attribution fidelity;
- temporal validity, stale-memory use and false-invalidation rate;
- revocation completeness, zombie-memory rate and revocation latency;
- recovery closure across state, holders and decisions;
- privacy leakage, false blocking and under-admission;
- token, compute, storage, bandwidth, latency, verifier and repair costs.

The strongest memory baseline must include a well-engineered single-agent proactive memory manager, not just naive RAG. The federation must also be compared with local per-agent stores, shared stores, event-sourced state, causal-graph memory and transactional governance under matched information and cost budgets.

## 7. What is supported, inferred and unresolved

### Supported in bounded settings
- Proactive memory maintenance can improve long-horizon state tracking in single-agent settings (UMA).
- Causal structure can improve retrieval over agentic trajectories (AMA-Bench).
- Return-time memory admission can jointly preserve valid information and reject stale information in tested settings (TRACE).
- Transactional state machines can enforce bounded protocol invariants and reduce downstream harm in controlled scenarios (MemTX).
- Memory lifecycle gates can reduce tested poisoning propagation (MAPLE-Guard).
- Poisoned memories can persist and affect later tasks across multiple memory backends (MemoryDojo).
- Collective false memories can emerge in controlled multi-agent settings (MANBENCH).

### Inference for the Holobiont
- The Hippocampus should be one specialist within a larger governance plane.
- Persistent memory links should be tracked separately from visible communication edges.
- The Narrative Thread should be a versioned projection over source events, not a sole authority.
- Memory admission should consider the receiving organ's role and downstream consequences, not only the producer's utility.
- Revocation and recovery must be designed during memory formation because missing lineage cannot reliably be reconstructed later.

### Unresolved
- Whether a collective-state plane improves a heterogeneous federation over a single-agent proactive memory system with the same evidence.
- Whether provenance and validity survive learned latent compression and cross-model bridges.
- Whether semantic conflict resolution can be trusted when there is no objective verifier.
- Whether a memory can be safely revoked across many agents while preserving independently supported conclusions.
- Whether recovery closure remains tractable at large scale and under partial outages.
- Whether the additional governance cost is justified by measurable reductions in harm and stale reliance.

## 8. Priority experiments

1. **E35-A — Collective-state lifecycle microbenchmark:** three organs (producer, consumer, auditor), with controlled admission, scope, propagation, conflict, revision, revocation and recovery events.
2. **E35-B — Return after state change:** an organ leaves, the others update shared facts, and the organ rejoins. Compare restore, reset, static memory, timestamp-only checks, TRACE-like admission and event-sourced current-state reconstruction.
3. **E35-C — Cross-agent memory poisoning:** inject a malicious observation through an ordinary document/tool result, summarize it, promote it to shared memory and test whether a later organ acts on it. Compare no defense, write-only, retrieval-only, lifecycle gates, authority gates and transaction commit.
4. **E35-D — Provenance laundering:** paraphrase untrusted evidence until its surface text looks like user-approved history. Test whether source authority survives summaries, latent bridges and derived records.
5. **E35-E — Concurrent updates:** inject stale late writes, dirty reads, permission laundering and semantic conflicts. Compare last-write-wins, snapshot isolation, semantic transaction and typed commit/repair.
6. **E35-F — Revocation and recovery closure:** revoke a root item and trace every derived summary, private copy, shared copy, plan and action. Measure state, holder and decision closure.
7. **E35-G — False forgetting and under-admission:** introduce resolver errors. Compare hard deletion, quarantine, supersession, soft retention and revalidation. Measure false-drop harm and stale-use harm separately.
8. **E35-H — Collective utility:** compare producer-only memory reward, audience-aware reward and team-level reward. Measure whether a memory that helps its author harms downstream organs.

## 9. Overall conclusion

The strongest update to the Cognitive Holobiont is that persistent memory must be treated as **governed collective state**, not as a passive shared database and not as a single organ's private recollection.

The project needs to remember, but it also needs to know:
- who created each memory;
- what it was derived from;
- who may rely on it;
- when it was valid;
- what changed it;
- what it caused other organs to believe or do;
- how to revoke and repair it.

The most important gap is now sharply measurable: can the Holobiont achieve high revocation and recovery closure while retaining valid memories, avoiding false deletion, resisting poisoning and staying within a matched resource budget?

No result in this pass demonstrates a complete collective identity, consciousness, immortality or general self-repair. The findings justify a more rigorous memory-governance research program, not a claim that the full organism already exists.
