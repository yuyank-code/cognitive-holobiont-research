# Experiment Backlog — Pass 34: Communication Fabric and Fault-Aware Routing

## E34-A — Communication fault contract

**Question:** Can a small organ network detect failures that leave messages parseable?

Build a two- or three-organ network with explicit evidence contracts. Inject crash, omission, truncation, partial-content, stale replay, semantic corruption, context expiry and malformed tool-call arguments at every handoff stage.

Compare:
- no validation;
- schema-only validation;
- completeness/evidence-contract validation;
- independent receiver validation;
- receiver validation plus fresh reacquisition.

Measure exposure, detection, propagation, final task outcome, silent-failure rate, time-to-detection and overhead.

## E34-B — Route redundancy versus evidence redundancy

Create four variants:
1. one path;
2. multiple paths carrying the same upstream evidence;
3. multiple paths with independent source acquisition;
4. independent specialist corroboration plus a provenance-aware verifier.

Inject faults before and after branching, at the shared source, in one branch, in the verifier and across all branches. Measure R_route, R_evidence, evidence cut, task success and false confidence.

Critical control: a duplicated message must not be counted as an independent source.

## E34-C — Full broadcast versus selective memory

Compare full-context broadcast, static role routing, RCR-style role/task-stage/token routing and risk-aware adaptive routing.

Tasks must include cases where the relevant memory is obvious and cases where a seemingly irrelevant memory becomes critical later. Measure:
- token and runtime cost;
- omission of critical context;
- duplicate exposure;
- memory poisoning propagation;
- temporal invalidation and stale-memory use;
- privacy leakage across organs.

Match the total information and verifier budgets.

## E34-D — Message format selection

Compare natural-language handoff, typed dependency graph, fixed hybrid, router-selected hybrid, structured shared memory and latent bridge.

Use both rigid evidence-contract tasks and ambiguous reasoning tasks. Include graph-aware and graph-unaware executor controls. Hold task evidence constant and account for router tokens, decoding, serialization and verification.

A latent bridge wins only if it adds causal task-relevant information or lowers total cost without worsening calibration, provenance or recovery.

## E34-E — Repair versus resample

Use recorded traces and intervention anchors. Compare:
- whole-trajectory rerun;
- deterministic replay to anchor plus downstream resampling;
- symptom-driven targeted intervention;
- fresh evidence reacquisition;
- rollback to last-valid state.

Report failure reproduction separately from repair. Validate on held-out task contracts and verify that repair does not corrupt memory or adjacent organs.

## E34-F — Fault-aware topology adaptation

Train/optimize a router using task competence, evidence criticality, source ancestry, failure-domain diversity, latency and token cost. Test on held-out tasks and fault classes. The router must not receive the injected fault label.

Compare static topology, random rewiring, task-only routing, risk-aware routing and oracle routing. Measure resilience, task quality, communication cost, route churn and instability.

## E34-G — Common-mode source and codec compromise

Poison a shared retrieval index, shared model family, latent codec, task-state bus, or memory schema. Compare independent model families, independent retrieval sources, signed/versioned records, and shared-only architectures.

Measure whether apparent redundancy survives correlated failure. Include a condition where every organ trusts the same wrong source.

## Pass/fail criteria

A communication-fabric change is not accepted merely because it improves nominal benchmark accuracy. It must improve one or more of:
- task utility under faults;
- evidence availability;
- silent-failure rate;
- validated recovery rate;
- false-recovery rate;
- cost-adjusted performance;

without unacceptable regressions in privacy, safety, latency, or specialist independence.
