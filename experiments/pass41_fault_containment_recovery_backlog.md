# Experiment Backlog — Pass 41: Fault Containment and Recovery

## Minimal test system

Use 3–5 independently instantiated organs:
- planner/executive;
- two specialist workers with distinct inputs or tools;
- aggregator/verifier;
- optional memory/security observer.

Include a deterministic tool, versioned shared memory, trace/provenance journal, and an external-effect simulator. Keep the first test small; increase model heterogeneity and persistence only after the basic fault lifecycle is measurable.

## Experiment 1 — Reproduce controlled fault injection

Faults:
- malformed structured output;
- schema-valid but semantically wrong output;
- tool timeout/unavailability;
- stale or corrupted tool result;
- wrong recipient / delayed message;
- context truncation;
- faulty planner decomposition;
- faulty aggregator;
- silent guardrail bypass.

Inject at chosen role and step with deterministic seeds. Keep injection metadata hidden from the runtime detector.

## Experiment 2 — Separate detection from containment

Alert conditions:
- oracle alert with correct origin;
- detector alert with predicted origin and confidence;
- symptom-only alert;
- delayed alert;
- no alert.

Containment baselines:
- no containment;
- source-only cancellation;
- full workflow halt;
- restart/rollback whole workflow;
- branch quarantine;
- provenance-guided selective cut;
- local deterministic egress fencing.

Report post-alert effects and healthy-work retention separately.

## Experiment 3 — Detector comparison

Compare:
- deterministic schema/type/invariant checks;
- telemetry thresholds;
- statistical anomaly detection;
- zero-shot LLM trace diagnosis;
- few-shot LLM diagnosis;
- specialized trained detector;
- ensemble of detector types.

Include no-fault traces and report false-positive rate, calibration, abstention, type@k, location@k, joint@k and detection latency.

## Experiment 4 — Control-plane fault injection

Inject failure/compromise into:
- Heart/coordinator;
- provenance journal or DAG;
- authorization root;
- site daemon/effect gateway;
- monitor;
- repair executor;
- verifier;
- shared clock/version service.

Include network partitions, delayed replication, duplicate events and inconsistent snapshots. Test whether local guards remain safe without the coordinator.

## Experiment 5 — Repair strategies under equal recovery budgets

Compare:
1. retry unchanged;
2. retry with altered plan;
3. recompute from trusted inputs;
4. rollback and replay from last clean checkpoint;
5. substitute another specialist;
6. repair adapter/readout;
7. restore checkpoint/replica;
8. retrain or distill from surviving information.

Match total compute, tool calls, tokens, latency deadline and verifier budget. Use repeated fault-free runs to estimate stochastic baseline variance.

## Experiment 6 — Taint closure and memory re-entry

Inject a poisoned artifact, let it propagate into summaries and multiple organ memories, then alert. Verify that:
- every descendant is found;
- pending effects are fenced;
- derived summaries are revoked or rebuilt;
- the repaired organ does not reload stale memory;
- a clean organ can still use independent valid evidence.

## Experiment 7 — Operational-profile robustness

Vary task mix, fault mix, fault timing, consequence weights, alert delays and concurrency. Estimate reliability envelopes and confidence intervals. Do not tune on the held-out profile.

## Experiment 8 — Scaling and control-plane availability

Scale from 3 to 5, 10, 20 and more organs. Measure journal throughput, provenance growth, detection delay, cut computation, local enforcement latency and coordinator failover. Compare centralized, replicated and hierarchical control planes.

## Experiment 9 — Adaptive adversary

After establishing a baseline, allow an adversarial organ to:
- produce plausible but wrong outputs;
- manipulate its telemetry;
- exploit missing lineage;
- send validly signed but dishonest outputs;
- induce alert fatigue;
- target the coordinator or verifier.

Separate cryptographic authenticity from semantic truth.

## Priority order

P0: experiments 1–3.  
P1: experiments 4–6.  
P2: experiments 7–9.

No larger self-regenerating architecture should be attempted until P0 demonstrates reliable detection/containment and P1 demonstrates state closure and safe re-entry.
