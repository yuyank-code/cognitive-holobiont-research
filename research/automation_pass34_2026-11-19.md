# Cognitive Holobiont Research — Pass 34
**Date:** 2026-11-19  
**Focus:** The connective tissue as a reliability-critical information network: communication faults, evidence-path redundancy, selective context routing, adaptive message formats, and causal recovery.

## Executive conclusion

This pass investigates how the Holobiont's organs should communicate and remain useful when communication is incomplete, corrupted, delayed, stale, or routed through a failed component. This is not a generic multi-agent survey: the question is whether the proposed connective tissue can preserve trustworthy task-relevant information while avoiding the cost and correlated failure of indiscriminate all-to-all sharing.

The strongest new evidence supports five design corrections:

1. **Communication is a failure surface, not just a connection.** A message can remain syntactically valid while losing essential evidence. In a 2026 preprint covering more than 29,000 executions, 20.7% of failures with complete detection records were silent; the rate reached 76.2% for partial-content faults.
2. **Redundant routes help only when they preserve an unaffected information dependency.** A flat workflow retained 53.0% success under the paper's injected communication faults versus 3.3% sequential and 3.2% hierarchical. The benefit was concentrated at evidence handoff, where an alternate branch already held the evidence. It disappeared when the fault occurred before the branch diverged or affected all evidence paths.
3. **Selective, role-conditioned sharing is a credible alternative to a continuously broadcast latent bloodstream.** Peer-reviewed EMNLP Findings work reports 35% fewer tokens and 38% lower runtime than full-context sharing while maintaining or improving task performance on its evaluated tasks.
4. **A hybrid message fabric is more defensible than choosing text or structure universally.** Peer-reviewed EMNLP Findings work uses a small router to choose between typed dependency graphs and natural language per delegation. Graph-only can regress on adaptive tasks; natural-language-only spends substantial tokens.
5. **Retries are not repairs.** A 2026 preprint reports that unguided reruns repaired only 6.90% of failed trajectories; symptom-driven intervention repaired 20.15%. Recovery needs trace anchors, failure localization, and access to trustworthy evidence.

The updated architecture hypothesis is therefore a provenance-aware, selectively routed, hybrid communication fabric with alternative evidence acquisition paths, explicit completeness checks, and trace-based recovery. This does not demonstrate that hidden-state bridges are unnecessary, but it raises the baseline they must beat. No new result establishes that a continuous latent bloodstream is superior to structured shared state.

---

## 1. Project-specific question

The originating Treatise proposes pairwise learned latent bridges, a shared bloodstream carrying task embeddings, uncertainty, resource consumption and summary latents, and a Narrative Thread for continuity. These mechanisms are intended to make the specialist organs function as one persistent cognitive system.

This pass asks:

- What fails when organs exchange information over real protocols and model endpoints?
- When does topology redundancy preserve information rather than merely duplicate a corrupted message?
- Can selective context routing reduce the cost and noise of continuous sharing?
- Should communication use natural language, typed structures, latent representations, or a task-dependent combination?
- What does genuine recovery require after a communication failure?

The distinction between a communication route and the information carried on that route is central.

## 2. New evidence

### 2.1 When Messages Go Wrong — silent semantic and partial-content faults

**Status:** arXiv preprint, submitted 11 October 2026; not treated as peer-reviewed in this pass.  
**Authors:** Jinhao Zhou, Xiaoyu Zhang, Jiongchi Yu, Fahao Chen and Jun Wu.  
**Source:** https://arxiv.org/abs/2610.15459

The study reports more than 29,000 executions across 100 tasks, five domains, three workflow topologies and three model configurations. Its fault taxonomy spans communication disturbances such as non-delivery, deadlines, stale replay, partial-content delivery and semantic corruption.

Key findings:
- Among 8,335 failures with complete detection records, 20.7% remained silent: execution continued without an immediate failure signal and later produced an unsuccessful task outcome.
- The silent-failure rate reached 76.2% for partial-content faults and 26.3% for semantic corruption. Partial-content faults accounted for 69.6% of silent failures in that subset.
- Across applied faulted executions with known outcomes, Flat retained 53.0% task success, compared with 3.3% for Sequential and 3.2% for Hierarchical.
- This topology advantage was not a general benefit of adding edges. Flat retained a second route from worker evidence to the decision stage. It helped mainly when the fault happened after the alternate branch already held the needed evidence.
- The advantage became small when the fault occurred before that branch received the evidence. If every available evidence path was affected, recovery disappeared.
- Fresh evidence reacquisition could recover cases when an unaffected source/path remained available. Copying the same corrupted evidence did not.

Why it matters to the Holobiont:
- The connective tissue must validate semantic completeness, not merely successful delivery or parseability.
- A network graph with multiple paths is not automatically evidence-resilient. If all paths descend from one corrupted observation or model output, they share a common failure dependency.
- The bloodstream should distinguish telemetry from evidence. A confidence scalar or summary latent cannot substitute for the source material needed to justify a decision.

Boundary:
- The work studies three AutoGen workflow structures and particular task/model configurations, not a trained heterogeneous organ federation.
- Flat's alternate branch carries the same pre-interception worker evidence; it is path redundancy after a shared source, not independent evidence generation.
- The study is a preprint and needs independent replication.

### 2.2 AgentChaos — runtime fault injection as a reliability test

**Status:** peer-reviewed, Proceedings of the 41st IEEE/ACM International Conference on Automated Software Engineering (ASE 2026), 12–16 October 2026.  
**Authors:** Gou Tan et al.  
**DOI:** https://doi.org/10.1145/3832783.3837437  
**Source:** https://arxiv.org/abs/2608.06790

AgentChaos injects crash, omission and value faults into content and tool-call fields at the HTTP/API boundary. It evaluates 65 fault configurations across five architectural patterns, seven benchmarks, four task domains and four backbone models.

Key findings:
- All evaluated systems degraded under injected faults; pass@1 fell by as much as 50 percentage points in the reported configurations.
- A pipeline system was especially vulnerable when a first-stage fault propagated through every downstream stage; an iterative system could sometimes observe and correct earlier errors.
- Truncation and empty/omitted content could be more harmful than obvious crashes because they looked like weak model output rather than infrastructure faults.
- Rule-based diagnosis identified truncation with only 4.3% accuracy in the reported analysis. Overall diagnosis was also weak.
- The robustness ranking was similar across the tested backbone models, suggesting implementation and fault handling mattered at least as much as model choice.

Critical limits:
- The study reimplemented systems on Google ADK, so absolute scores may differ from original implementations.
- It evaluates only one system per architectural pattern, so pattern-level causal claims are not fully isolated.
- The 65 configurations are spread thinly across tasks; the authors note roughly 4.6 triggered tasks per configuration in one evaluation, creating variance.
- Its main outcome metric is pass@1 and does not capture all partial correctness or quality.

Holobiont implication:
- Instrument each organ call and each bridge handoff with response length, finish reason, token usage, schema validation, tool-call validation, trace identifiers and source lineage.
- Do not diagnose every bad output as a weak specialist. Some are transport, truncation, routing or evidence-contract failures.

### 2.3 RCR-Router — role-conditioned selective memory routing

**Status:** peer-reviewed, Findings of EMNLP 2026, pages 8938–8963.  
**Authors:** Jun Liu et al.  
**DOI:** https://doi.org/10.18653/2026.findings-emnlp.425  
**Source:** https://aclanthology.org/2026.findings-emnlp.425/

RCR starts with structured shared memory and role-specialized agents. It selects memory items for each agent according to role, optional task-stage metadata and a token budget. It iteratively updates memory rather than exposing every agent to all context.

Reported results:
- 35% average token reduction.
- 38% average runtime reduction relative to Full-Context.
- Performance maintained or improved on multi-hop QA, ALFWorld and WebShop.

Holobiont implication:
- A continuously broadcast bloodstream is not the only plausible way to share context.
- A memory router can decide which organ needs which item at which task stage.
- The Hippocampus-like memory can remain shared logically while access is selective and role-conditioned.

Boundary:
- The paper evaluates structured shared-memory routing, not long-term autobiographical continuity, provenance-aware deletion, adversarial memory poisoning, or hidden-state transfer.
- Its reported savings are benchmark-specific and should not be generalized to every workload.

### 2.4 Routed Graph Handoff — choose the message format per delegation

**Status:** peer-reviewed, Findings of EMNLP 2026, pages 42756–42765.  
**Authors:** Pratyay Banerjee and Ankit Chadha.  
**DOI:** https://doi.org/10.18653/2026.findings-emnlp.2008  
**Source:** https://aclanthology.org/2026.findings-emnlp.2008/

The paper reports that natural-language communication consumes 40–60% of the token budget in its studied multi-agent systems. Typed dependency graphs compress communication, but graph-only delegation can fail on tasks needing adaptive reasoning. Routed Graph Handoff uses a small router (reported as 155 tokens, 0.15% overhead) to select between a typed dependency graph and natural language per delegation.

Reported results on four benchmarks and more than 1,050 trajectories:
- +12.7 percentage points on Tau-retail at 3.2× compression.
- +8.7 percentage points on BrowseComp at 2.2× compression.
- Parity on BFCL and AppWorld.
- Without the router, graph-only regressed 14.6 percentage points on AppWorld.
- A graph-aware executor prompt was necessary; the same schema without interpretation guidance produced no gain.

Holobiont implication:
- Use typed structures for stable, machine-checkable dependencies, evidence IDs, task state and action arguments.
- Use natural language when the recipient must reason flexibly about ambiguity, alternatives or novel context.
- A router should choose the representation based on task needs, not impose one universal communication format.

This work does not test latent-state bridges. It creates a stronger structured/hybrid baseline those bridges must outperform.

### 2.5 RouterHGC — collaboration-aware routing

**Status:** peer-reviewed, Findings of ACL 2026, pages 31759–31789.  
**Authors:** Yitao Xiao et al.  
**DOI:** https://doi.org/10.18653/v1/2026.findings-acl.1589  
**Source:** https://aclanthology.org/2026.findings-acl.1589/

RouterHGC models queries, collaboration modes, agent roles and model choices in a heterogeneous graph, using graph contrastive learning to select an agent combination and collaboration mode.

Reported results:
- 0.80%–6.17% accuracy gains on MATH and HotpotQA relative to the reported best single LLM and baselines.
- 27.40% lower inference cost in its experiments.

Holobiont implication:
- The Heart should not activate every organ for every task.
- Routing should select a task-conditioned subset of organs and communication pattern.
- Cost-aware routing is a necessary baseline before claiming that a larger federation creates value.

Boundary:
- These results are from five public datasets and do not establish robustness under component failure, persistent memory, or long-running organ populations.

### 2.6 Repair or Resample? — causal repair versus stochastic rerun

**Status:** arXiv preprint, submitted 26 August 2026, revised 29 August 2026.  
**Authors:** Zhongwen Luan et al.  
**Source:** https://arxiv.org/abs/2608.25920

The authors introduce SymTrace, which records execution trajectories and intervention anchors, and SymFail, a dataset of 536 human-annotated failure trajectories with graph-linked locations, categories and trace evidence.

Reported findings across three MAS frameworks:
- Unguided reruns reproduced failures at 67.97% and repaired only 6.90% of failed cases.
- A symptom-driven intervention repaired 20.15% of failed cases.

Holobiont implication:
- Restarting an organ or resampling a whole network is not evidence of self-healing.
- The system needs traceable causal anchors, localized symptom classification, and targeted intervention.
- Recovery must be tested against the same failure conditions and held-out task contracts, not judged by a lucky successful rerun.

Boundary:
- Preprint, limited to the studied frameworks and intervention method; the reported repair rate is still only a minority of failed cases.
- This is trajectory-level MAS debugging, not neural specialist regeneration.

---

## 3. Cross-paper synthesis

These studies converge on an architectural principle:

**The unit of resilience is not the edge or the agent. It is the trustworthy information dependency.**

A network can have many communication paths but still be fragile if all paths originate from the same corrupted observation, model family, memory record or compromised bridge. Conversely, a small number of carefully routed paths can be robust if at least one can reacquire trustworthy evidence independently.

The new evidence supports:
- fault-aware communication contracts;
- stage-level validation;
- role-conditioned context selection;
- hybrid typed-graph/natural-language handoffs;
- task-conditioned organ activation;
- alternative evidence acquisition;
- trace-based diagnosis and recovery.

It does not establish:
- that all-to-all latent sharing is better than selective structured messages;
- that a shared latent space guarantees semantic equivalence;
- that majority or receiver-side consensus makes a message true;
- that topology redundancy survives common-source corruption;
- that the Holobiont creates emergent cognitive synergy.

## 4. Revised architecture hypothesis

Replace the Treatise's implied always-on broadcast model with a staged communication fabric:

1. **Local processing:** organs retain independent representations and produce evidence with provenance.
2. **Task-state publication:** organs publish compact status and uncertainty telemetry separately from factual evidence.
3. **Selective context routing:** the Heart routes only relevant memory/evidence to each organ under a token and risk budget.
4. **Adaptive handoff format:** typed graph/schema for stable dependencies and action contracts; natural language for ambiguity and novel reasoning; latent bridges only when task-specific causal transfer is demonstrated.
5. **Evidence admission:** recipients validate required fields, source lineage, freshness, schema version and completeness before using a message.
6. **Alternative acquisition:** where evidence is critical, maintain an independent source or reacquisition route—not merely another copy of the same sender's output.
7. **Trace-based recovery:** log causal anchors, replay to the last valid state, localize the failure, reacquire or regenerate the affected evidence, then verify.
8. **Topology adaptation:** route around a failing edge or source only when the alternative route has a genuinely different failure dependency.

The Narrative Thread should be represented as a versioned event/state history with temporal validity and provenance, not as a single opaque latent whose correctness cannot be audited. A learned latent summary may be stored alongside this explicit record, but should not replace it.

## 5. Mathematical additions

Let each evidence item e have:
- source identity s(e);
- ancestry/lineage A(e);
- creation time t(e);
- validity interval V(e);
- schema/version v(e);
- integrity state g(e);
- task relevance r(e).

A message is admissible only if its required fields are complete, its source is authorized, its lineage is traceable, and it is valid for the current task/time.

Define route redundancy and evidence redundancy separately:

- R_route: number of edge-disjoint routes to a decision node.
- R_evidence: number of sufficiently independent evidence origins that can support the decision.
- K_evidence: minimum number of independent source/failure domains whose removal disconnects all admissible evidence from the decision.

A duplicated copy can increase R_route while leaving R_evidence and K_evidence unchanged.

For a fault f, define:
- SFR(f): probability of final task failure without immediate detection, conditioned on f being applied.
- A_e(f): probability that at least one admissible evidence path remains.
- R_s(f): probability of validated recovery after f.
- F_r(f): probability the system declares recovery although held-out evidence/task contracts still fail.

A communication strategy should be evaluated by a vector, not one accuracy score:
U = (task utility, silent-failure rate, evidence availability, recovery success, false recovery, latency, tokens, memory, bandwidth, verifier cost).

## 6. Falsification conditions

The revised connective-tissue hypothesis is weakened if:
- selective routing fails to reduce cost or improve task quality versus full-context under matched information access;
- typed/hybrid handoffs fail to outperform the best fixed format on held-out task classes;
- latent bridges do not causally transfer information beyond structured messages and shared-memory retrieval at matched budgets;
- apparent route redundancy collapses when faults are injected at shared upstream sources;
- evidence provenance does not predict which recovery paths remain valid;
- trace-based interventions do not outperform unguided reruns when replay and evaluation budgets are matched;
- adaptive routing improves benchmark score but increases silent failures, false evidence acceptance, or safety regressions.

## 7. Next experiments

Priority order:

**E34-A — Communication fault contract.** Build a two- or three-organ test network. Inject crash, omission, truncation, partial-content, stale replay, semantic corruption, context expiry and invalid tool-call arguments at each handoff stage. Measure detection latency, silent failures, downstream propagation and final task outcome.

**E34-B — Route redundancy versus evidence redundancy.** Compare: (i) one path, (ii) multiple paths carrying the same source evidence, (iii) multiple paths with independent source acquisition, and (iv) independent specialist corroboration. Inject faults before and after branching and into shared upstream sources.

**E34-C — Full broadcast versus selective memory.** Compare full-context, static role routing, RCR-style role/task-stage/token routing, and adaptive risk-aware routing. Match total information access and verifier budget. Measure token/runtime cost, omitted-critical-context errors and privacy leakage.

**E34-D — Message-format selection.** Compare natural language, typed dependency graph, fixed hybrid, router-selected hybrid, structured shared memory and latent bridge. Use tasks with both rigid evidence contracts and genuinely ambiguous reasoning. Include a graph-aware executor control.

**E34-E — Repair versus resample.** Use deterministic replay anchors. Compare whole-trajectory rerun, downstream-only replay, symptom-driven intervention, fresh evidence reacquisition and rollback to a last-valid checkpoint. Report reproduction rate and actual repair rate separately.

**E34-F — Fault-aware topology adaptation.** Train or optimize the router using task competence, evidence criticality, source ancestry, failure-domain diversity, latency and token cost. Test on unseen tasks and correlated failures. Do not let the router inspect the injected fault label.

**E34-G — Common-mode source and codec compromise.** Poison a shared retrieval index, shared model family, latent codec, task-state bus or memory schema. Compare independent model families, independent retrieval sources, signed/versioned records and shared-only architectures. Measure whether apparent redundancy survives correlated failure, including a condition where every organ trusts the same wrong source.

## 8. Open questions

1. How should independence between evidence sources be estimated when organs share base models, training data, retrieval indexes or latent codecs?
2. Can the system detect a semantically incomplete but parseable message without a separate verifier becoming the new central failure point?
3. How should an organ express uncertainty about a missing evidence field versus uncertainty about the underlying fact?
4. Can temporal validity and provenance be preserved when a latent bridge compresses or transforms an evidence-bearing representation?
5. What is the minimum number and diversity of sources required for safe recovery under a given threat model?
6. How should dynamic topology avoid feedback loops, duplicated work and selective-information blind spots?
7. Which tasks truly benefit from hidden-state communication after a strong structured/hybrid baseline is available?

## 9. Bottom line

The connective tissue should not be designed as an always-open bloodstream that sends everything everywhere. It should be a controlled information network: selective, typed where possible, expressive where necessary, provenance-aware, fault-injected, and able to reacquire evidence independently.

This is a meaningful refinement of the original Holobiont vision. It preserves the ambition of continuous cooperation and resilience while replacing unverified assumptions about latent telepathy and redundant connectivity with measurable information-flow guarantees.
