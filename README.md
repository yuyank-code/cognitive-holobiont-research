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

The originating document, `The_Cognitive_Holobiont_Treatise.pdf`, is the project's initial vision and hypothesis specification. It is **not** treated as established scientific fact.

## Latest research pass

Pass 28 — 2026-10-18 adds a dependence-adjusted effective-team-size lens, distinguishes answer diversity from useful evidence, audits memory-ablation identifiability, and records scenario-specific evidence that protocol choice affects latency and fault recovery. It does not establish a task-general scaling law or Holobiont-specific synergy.

Artifacts:
- `research/automation_pass28_2026-10-18.md`
- `research/claim_evidence_matrix_pass28_addendum.md`
- `research/contradictions_open_problems_pass28.md`
- `mathematics/pass28_effective_team_size_and_memory_identifiability.md`
- `sources/pass28_source_ledger.md`
