# Falsification Framework — Pass 41

## Claim under test

A Cognitive Holobiont-style federation can detect, localize, contain, recover from and safely reintegrate after faults more effectively than simpler agent workflows, without sacrificing more healthy work or introducing a new single point of failure.

## Required baselines

- single model with deterministic tool checks;
- static planner/worker/aggregator;
- retry-only;
- full restart/rollback;
- source-only cancellation;
- centralized monitor and quarantine;
- provenance-guided selective containment;
- replicated/local enforcement control plane;
- model-assisted diagnosis plus deterministic enforcement.

## Falsification conditions

Reject or narrow the resilience claim if:
1. Under hidden injected faults, the detector cannot exceed a simple invariant monitor on the relevant fault class.
2. Selective containment does not reduce weighted post-alert blast radius relative to source-only cancellation.
3. Healthy-work retention is not better than full quarantine at matched safety.
4. Symptom-only alerts force whole-system halt in most realistic cases.
5. Coordinator, provenance store or authority-root failure disables local effect fencing.
6. False-positive quarantine cost exceeds the value of avoided failures under the operational profile.
7. A correct final answer is produced but tainted memory or pending actions remain reusable.
8. Repair success cannot be distinguished from stochastic rerun success.
9. Reintegrated organs regress safety, calibration, authorization or prior task performance.
10. The federation's total recovery cost exceeds a simpler baseline without a compensating safety or availability gain.

## Non-negotiable reporting

- Fault injection point and detection point must be separate.
- Include silent semantic corruption and no-fault controls.
- Report pre-alert harm, post-alert preventable harm and post-fence leakage.
- Report detector false positives and false negatives.
- Report root-cause localization, not just fault-type classification.
- Count recovery only after independent final-state and memory-lineage verification.
- Include control-plane failures and shared dependencies.
- Publish all seeds, fault configs, traces, exclusions and failed runs.

## Evidence threshold

A small bounded claim can be accepted if it is reproducible on held-out tasks and fault configurations, improves safety and healthy-work retention at a reported resource frontier, and does not rely on an oracle alert unless the claim is explicitly limited to post-alert containment.

A general claim of autonomous self-healing requires all stages to work without supplied fault origin labels and to survive faults in the detector, coordinator, memory and effect gateway.
