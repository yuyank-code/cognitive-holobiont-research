# Architecture Note — Task-Conditioned Federation
**Pass 37 · 2026-11-22**

## Design position

Do not activate every organ for every task. The federation should be a selectable operating mode whose expected value is estimated from task structure, evidence distribution, specialist capabilities and resource constraints.

## 1. Task profiler

Estimate:
- independent parallel work available;
- dependency depth and handoff sensitivity;
- context saturation;
- tool density and external state;
- evidence complementarity / private information;
- uncertainty and search-space breadth;
- availability of independent verification;
- expected failure cost and resilience value.

The profiler must expose uncertainty and abstain when its architecture choice is poorly calibrated.

## 2. Operating modes

### Mode A — Single-locus execution
Use one generalist or one specialist when the task is compact, fully contextualized, strongly sequential, or when expected coordination costs exceed the likely gain.

### Mode B — Parallel evidence acquisition
Activate multiple organs when work can proceed independently or when each organ has unique data, modality or expertise. Delay synthesis until evidence is returned; do not force premature consensus.

### Mode C — Centralized / hybrid integration
Use a coordinator when dependencies require ordering, shared constraints, validation or explicit conflict resolution. Permit limited peer links only where they serve a defined information dependency.

### Mode D — Persistent federation
Use durable specialists and governed memory for long-running tasks only when their retained state or capability provides measurable value beyond re-instantiating task agents or using a single long-context controller.

## 3. Evidence-preserving handoff contract

Every transfer should identify:
- task/subtask and dependency;
- source/evidence identifier;
- origin organ and model lineage;
- raw observation versus inference;
- confidence/calibration and known limitations;
- timestamp/version and scope;
- what remains unresolved;
- required validation or downstream action.

The receiving organ should be able to request missing evidence, reject stale context and preserve dissent.

## 4. Architecture selection objective

Choose the mode that maximizes expected task utility under a declared resource vector. Safety and permissions are constraints. Do not use the ~45% baseline-accuracy pattern from one study as a fixed threshold.

## 5. What this is not

This note does not prescribe a final organ roster, latent codec, hypernetwork, self-modification system or implementation. It is a testable intermediate architecture hypothesis that can be compared against single-agent, best-of-K, MoE, fixed MAS and learned routing baselines.
