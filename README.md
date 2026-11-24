# Cognitive Holobiont Research

## What this research is about

The Cognitive Holobiont is a long-term research project exploring whether intelligence can be built as a distributed, organism-inspired system rather than as one monolithic AI model. The central research question is:

**Can a federation of independent, specialised AI models cooperate, preserve knowledge, withstand component failures, repair lost capabilities, and reorganise itself over time in ways that are measurably better than existing AI architectures?**

The project takes inspiration from biological organisms and the Society of Mind: different specialised components perform different functions, communicate, share selected information, and collectively sustain a larger system. The biological analogy is a source of hypotheses—not evidence that the proposed architecture will work.

## The problems being investigated

The research examines whether a distributed architecture can reduce or improve on:
- dependence on one central model and its associated failure points;
- poor routing of work across specialised capabilities and inefficient use of compute;
- hallucinations, correlated errors, adversarial compromise, and unreliable consensus;
- loss of useful knowledge when a component is damaged, replaced, or removed;
- fragile memory and loss of continuity across long-running tasks;
- difficulty safely adapting the system's own structure as requirements change.

## The proposed system

The originating treatise describes a federation of specialist models, metaphorically called **organs**. Example roles include vision, audio, anomaly detection, action and tool execution, process control, memory, security, fast formal reasoning, orchestration, and executive planning. These are illustrative roles; research may revise or replace them.

The proposed architecture has several connected research themes:

1. **Specialist organs:** independent, heterogeneous models with local expertise, autonomy, and task-specific capabilities.
2. **Connective tissue:** learned bridges between models' latent spaces, alongside explicit messages and compact shared state. The research tests when hidden-state communication transfers useful information and when structured communication is preferable.
3. **Hypernetwork DNA:** shared or distributed generative mechanisms intended to create, adapt, or reconstruct specialist capabilities. A key question is whether a surviving component can recover another component's *capability*, not merely reload a backup.
4. **Distributed memory and continuity:** episodic and semantic memory, shared context, provenance, versioning, temporal validity, contradiction handling, and safe forgetting or retraction.
5. **Immune and fault-tolerance mechanisms:** detection, quarantine, robust evidence aggregation, and continued safe operation when components fail, drift, or behave adversarially.
6. **Self-healing and regeneration:** diagnosis of capability loss, repair or replacement, validation, and safe reintegration.
7. **Recursive self-modification:** a meta-controller that may propose changes to specialists, communication topology, memory, routing, and resource allocation. Such changes must be sandboxed, evaluated, reversible, and permission-gated.

## What the research must establish

This is not an assumption that a multi-agent system is automatically more intelligent. Each distinctive claim must be tested against strong alternatives, including:
- a single model given the same total compute and information;
- best-of-many sampling and conventional ensembles;
- mixture-of-experts systems;
- conventional multi-agent debate and collaboration;
- latent-space multi-agent communication;
- shared-context, task-queue, and verifier-based architectures.

Experiments should control for compute, memory, bandwidth, latency, information access, and verification budget. They should test causal contribution—not just correlation—including independent proposals, best-of-K selection, ablations, ownership swaps, topology interventions, adversarial and correlated failures, memory contamination, and held-out tasks.

The research must actively seek negative results, replication failures, competing explanations, and theoretical limits. It must distinguish:
- claims made in the original treatise;
- findings supported by external research;
- interpretations or design hypotheses;
- open questions and claims not yet demonstrated.

## Long-term ambition and scientific caution

The long-term ambition is a modular, workload-distributed, fault-tolerant, continuously operating, self-monitoring, self-repairing, and adaptively reconfigurable intelligence system. General intelligence, consciousness, immortality, zero downtime, and complete regeneration are aspirations or hypotheses in the treatise—not established properties or guaranteed outcomes.

The goal of this research is to discover what is feasible, what is conditional, what is unsupported, and what may be impossible; then identify the smallest decisive experiments. **Do not rush into implementation before the evidence and falsification plan justify it.**

## Research programme and living records

Each substantive research pass should:
- investigate a clearly stated part of the project vision;
- add genuinely new, freely accessible, high-quality evidence and follow citation chains;
- include contradictory evidence, critiques, replications, and negative results;
- update the literature map, claim-evidence matrix, contradiction log, open questions, mathematical formalisation, architecture conclusions, falsification framework, and experiment backlog;
- revise earlier conclusions when stronger evidence appears;
- clearly label peer-reviewed research, preprints, and vendor claims;
- preserve findings in this repository and verify the resulting files and commit.

The originating document, The_Cognitive_Holobiont_Treatise.pdf, is the project's initial vision and hypothesis specification. It is **not** treated as established scientific fact.

## Latest research pass

**Pass 39 — 2026-11-24** investigates the Treatise's connective tissue: whether hidden representations transfer example-specific information across specialist organs, when latent channels beat text/typed evidence, and how to secure the payloads. New evidence includes two causal audits of latent communication (arXiv preprints), dense heterogeneous KV alignment (preprint), LatCom (EMNLP 2026), HyLaT (EMNLP 2026), architecture-dependent activation transfer (preprint), BOUNDARY_SYNC (preprint), and KV-cache integrity analysis (preprint).

The central conclusion is that latent transfer is conditionally feasible, not a universal shared language. Native KV relay can carry sender-private information when the receiver genuinely lacks it, but natural benchmark gains can be generic cache/interface effects rather than example-specific content. Learned cross-model adapters work for selected pairs, while other activation-transfer tests fail at the generation level. Latent compression and hybrid latent-text protocols are useful peer-reviewed efficiency/interface baselines, but remain limited by model size, same-family alignment, topology and opaque latent semantics. A text verifier cannot certify hidden-state payloads; transport authenticity and endpoint truthfulness are separate.

The recommended near-term design is a selective, auditable hybrid channel: local private reasoning by default; typed provenance and visible commitments as the control plane; latent transfer only when receiver necessity and measured utility justify it; pair-specific adapters with held-out validation; authenticated transport; and fail-closed text/typed-evidence fallback.

Artifacts:
- research/automation_pass39_2026-11-24.md
- research/claim_evidence_matrix_pass39_addendum.md
- research/contradictions_open_problems_pass39.md
- mathematics/pass39_latent_channel_causal_value.md
- experiments/pass39_latent_channel_audit_backlog.md
- falsification/pass39_latent_communication.md
- sources/pass39_source_ledger.md
- literature_map/pass39_latent_communication.md
- architecture/pass39_auditable_hybrid_connective_tissue.md

**Pass 36 — 2026-11-21** investigates the Meta-Organ and safe recursive self-modification. New evidence includes MetaGen (Findings EMNLP 2026), Multi-Agent Evolve (EMNLP 2026), AgentConductor (ICML 2026), Adaptive Graph Pruning (ECAI proceedings), MANTA (preprint), SEABench (preprint), an evolution-native security analysis, and a study of reward hacking in autonomous research agents.

The central conclusion is that task-conditioned role/topology adaptation and bounded runtime graph repair now have experimental support in selected settings. But these methods mostly adapt text-level roles or communication graphs around a shared backbone; they do not demonstrate safe evolution of a heterogeneous population of independent specialist organs. Persistent evolution can also collapse or create downstream safety regressions. The proposed Meta-Organ should therefore be a least-privilege proposal-and-validation service, with typed mutations, deterministic schema/permission checks, sandbox replay, independent evaluation, canary deployment and verified rollback. Start with topology-only changes; do not grant direct weight, evaluator, permission or constitutional write access.

Artifacts:
- research/automation_pass36_2026-11-21.md
- research/claim_evidence_matrix_pass36_addendum.md
- research/contradictions_open_problems_pass36.md
- mathematics/pass36_safe_meta_organ.md
- experiments/pass36_meta_organ_backlog.md
- falsification/pass36_self_modification.md
- sources/pass36_source_ledger.md
- literature_map/pass36_meta_organ_evolution.md
- architecture/pass36_governed_meta_organ.md

## Earlier research pass details

**Pass 35 — 2026-11-20** investigates the Hippocampus, Narrative Thread and shared-memory vision as a problem of governed collective state. New evidence includes the OTGE survey of 89 LLM-agent papers, UMA (EMNLP 2026), AMA-Bench (ICML 2026), TRACE, MemTX, MAPLE-Guard, MemoryDojo, MANBENCH (ICLR 2026) and provenance-preserving memory controls.

The central conclusion is that a shared store is not enough: the Holobiont needs a cross-cutting Collective State Plane that governs admission, scope, propagation, reconciliation, revision, revocation and recovery. Memory must preserve provenance, authority, temporal validity and typed dependencies. A memory write is not a belief commit, and a retrieved memory is not automatically action-safe. The literature is much stronger on memory creation/retrieval than revocation and recovery; the cited survey reports only 12 of 89 papers address revocation and 6 address recovery.

Artifacts:
- research/automation_pass35_2026-11-20.md
- research/claim_evidence_matrix_pass35_addendum.md
- research/contradictions_open_problems_pass35.md
- mathematics/pass35_collective_memory_governance.md
- experiments/pass35_collective_memory_backlog.md
- falsification/pass35_collective_memory.md
- sources/pass35_source_ledger.md
- literature_map/pass35_collective_memory.md

**Pass 34 — 2026-11-19** investigates the connective tissue as a reliability-critical information network. New evidence covers silent semantic/partial-content communication failures (When Messages Go Wrong, arXiv preprint), runtime API fault injection (AgentChaos, ASE 2026), role-conditioned selective memory routing (RCR-Router, Findings EMNLP 2026), adaptive typed-graph/natural-language handoff (Routed Graph Handoff, Findings EMNLP 2026), collaboration-aware routing (RouterHGC, Findings ACL 2026), and trace-anchored causal repair versus stochastic reruns (Repair or Resample, arXiv preprint).

The central conclusion is that resilience depends on preserving trustworthy information dependencies, not merely adding network edges. Selective and hybrid communication now provide strong baselines for the Treatise's continuous latent bloodstream. Alternative routes help only when they retain an unaffected evidence path; copies of the same corrupted source do not create independent evidence. Retrying is not proof of repair.

Artifacts:
- research/automation_pass34_2026-11-19.md
- research/claim_evidence_matrix_pass34_addendum.md
- research/contradictions_open_problems_pass34.md
- mathematics/pass34_communication_reliability.md
- experiments/pass34_communication_fabric_backlog.md
- falsification/pass34_communication_reliability.md
- sources/pass34_source_ledger.md
- literature_map/pass34_communication_and_faults.md

**Pass 33 — 2026-11-18** investigated capability regeneration, localized model repair, Byzantine-resilient collaboration, and recoverable self-modification. Its artifacts remain available:
- research/automation_pass33_2026-11-18.md
- research/claim_evidence_matrix_pass33_addendum.md
- research/contradictions_open_problems_pass33.md
- mathematics/pass33_recoverability_and_fault_tolerance.md
- experiments/pass33_repair_and_byzantine_backlog.md
- sources/pass33_source_ledger.md

Earlier research:
- Pass 28 — research/automation_pass28_2026-10-18.md and its matrix, contradictions, mathematics and source ledger.
- Pass 32 — research/pass32-2026-10-22 branch contains a memory-governance claim-matrix addendum and a short report stub; it is not represented as a complete main-branch research pass.

## Research discipline

Preserve null and contradictory evidence. Match total resources and information access. Separate temporal currency, evidence support, authorization, retrieval, verified utility, fault recovery, and total cost. Do not infer Holobiont-specific synergy from message volume, consensus, provenance, or benchmark headline scores alone.


**Pass 37 — 2026-11-22** investigates whether the Cognitive Holobiont's federation creates measurable value beyond extra inference compute, parallel sampling or better orchestration. New evidence includes *Towards a Science of Scaling Agent Systems* (arXiv preprint), Tran & Kiela's equal-thinking-token comparison (preprint), BenchAgent (preprint), OrchBench (preprint), SC-MAS (preprint), Riedl's *Emergent Coordination in Multi-Agent Language Models* (ICLR 2026), a Pareto test-time-scaling study (ACL 2026 Student Research Workshop), and a peer-reviewed compact-context rover benchmark (Frontiers, July 2026).

The central conclusion is that multi-agent value is task-contingent, not monotonic in agent count. Parallelizable subtasks and genuinely complementary/private evidence can justify federation; compact fully observed tasks and strict sequential reasoning can lose to a single strong model after coordination overhead. Measured emergence or information-theoretic synergy does not automatically imply external task utility. Resource parity must be treated as a vector (compute, tokens, latency, context, bandwidth, information/tools and verifier budget), and claims must survive best-of-K, single-model multi-output and MoE/router baselines.

The proposed intermediate architecture is a task-conditioned federation with single-locus, parallel-evidence, centralized/hybrid and persistent-federation modes. The next decisive experiment is a private-evidence partition with ownership swaps and a multi-dimensional resource frontier. No universal agent-count threshold or general superiority claim is supported.

Artifacts:
- research/automation_pass37_2026-11-22.md
- research/claim_evidence_matrix_pass37_addendum.md
- research/contradictions_open_problems_pass37.md
- mathematics/pass37_collective_value_and_budget_parity.md
- experiments/pass37_federation_advantage_backlog.md
- falsification/pass37_collective_advantage.md
- sources/pass37_source_ledger.md
- literature_map/pass37_collective_intelligence_evaluation.md
- architecture/pass37_task_conditioned_federation.md


**Pass 38 — 2026-11-23** investigates effective organ independence, response diversity and common-mode failure. New evidence includes Morante & Romero García-Rubio's *Correlation limits the reliability of ensemble decision making with large language models* (Discover Informatics, 4 November 2026), Tieman & Markou's output-derived generative-process diversity audit (arXiv preprint), Donghwan Kim's capability-controlled diversity-metric audit (arXiv preprint), D-FUSEr (ICML 2026), HiddenBench (ICML 2026), and Self-Anchored Consensus (preprint).

The central conclusion is that **functional complementarity and response diversity are different objectives**. Complementary specialist organs add distinct capabilities or private evidence; redundant backups for overlapping critical functions should fail differently under matched perturbations. Provider count, model count, semantic output distance and prompt variation do not establish independent failure behavior. The new effective-voter formula is a variance-based diagnostic under explicit assumptions, not a universal information or intelligence count.

The proposed Resilience-Aware Organ Population maintains a capability map, a task/failure-specific co-failure map, and a dependency/provenance graph spanning weights, data lineage, evaluators, prompts, memory, codecs, hypernetworks, tools and infrastructure. The next decisive milestone is an organ-independence audit followed by common-mode fault injection and repair tests under shared-dependency compromise.

Artifacts:
- research/automation_pass38_2026-11-23.md
- research/claim_evidence_matrix_pass38_addendum.md
- research/contradictions_open_problems_pass38.md
- mathematics/pass38_effective_organ_independence.md
- experiments/pass38_common_mode_diversity_backlog.md
- falsification/pass38_independence_and_resilience.md
- sources/pass38_source_ledger.md
- literature_map/pass38_effective_diversity.md
- architecture/pass38_resilience_aware_organ_population.md
