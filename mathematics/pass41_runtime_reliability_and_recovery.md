# Mathematical Formalization — Pass 41: Runtime Reliability and Recovery

## 1. Fault lifecycle

For a fault event f define:
- t_f: fault occurrence/injection time;
- t_D: valid alert time;
- t_L: root-cause localization time;
- t_C: time all relevant containment fences are confirmed;
- t_R: recovery/repair completion time;
- t_V: independent revalidation completion time.

Latencies:
- Detection: Δ_D = t_D - t_f
- Localization: Δ_L = t_L - t_D
- Containment: Δ_C = t_C - t_D
- Repair: Δ_R = t_R - t_C
- Validation: Δ_V = t_V - t_R

These should be reported separately; a single “recovery time” hides the stage that limits the system.

## 2. End-to-end safe recovery

By the chain rule:

P(SafeRecovery) = P(D) · P(L|D) · P(C|L,D) · P(R|C,L,D) · P(V|R,C,L,D)

This is a factorization, not an independence assumption. Each conditional term should be measured under the same operational profile and fault taxonomy.

## 3. Blast radius

Let A_f be the set of external effects or state transitions causally reachable from f. Let w_a be a consequence weight fixed before evaluation.

B_f = Σ_{a∈A_f} w_a · 1[a commits after alert and before confirmed containment]

Report:
- pre-alert committed harm separately;
- preventable post-alert harm;
- post-fence leakage;
- uncontained counterfactual blast radius.

Do not count blocked effects as completed work.

## 4. Containment and availability

Containment effectiveness:
C_f = 1 - B_f(contained) / B_f(uncontained)

Healthy-work retention:
H = W_healthy,completed / W_healthy,eligible

False-quarantine cost:
Q = W_healthy,stopped + λ·W_healthy,delayed + μ·W_healthy,discarded

Weights λ and μ must be specified by workload owners before testing.

## 5. Diagnosis

Fault-type accuracy and root-cause localization are separate:
- D_type@k = fraction of faults with true type in top-k.
- D_loc@k = fraction with true origin in top-k.
- D_joint@k = fraction with both correct in top-k.

Also report calibration, abstention, no-fault false-positive rate, and performance under symptom-only alerts.

## 6. Recovery closure

Let Desc(f) be all downstream records, memory entries, pending actions and derived artifacts whose lineage includes f.

Closure:
R_closure = |{x∈Desc(f): x is corrected, compensated, revoked or safely blocked}| / |Desc(f)|

This is stricter than task retry success. A run that returns a correct final answer while retaining poisoned downstream memory is not fully recovered.

## 7. Availability and control-plane common cause

Model the control plane as components:
- telemetry/journal;
- provenance store;
- detector;
- authority/permission service;
- local effect gateway;
- coordinator/replicated state;
- repair executor;
- independent verifier.

A series-path approximation can be useful for fault-tree construction, but shared dependencies and common-cause events must be modeled explicitly. Do not multiply marginal component reliabilities as if independence were guaranteed.

For an operational profile Ω over task classes x and fault conditions f:
R_sys(Ω) = Σ_x Σ_f P_Ω(x,f) · P(SafeOutcome | x,f)

When Ω is uncertain, report a reliability interval/envelope rather than a single point estimate.

## 8. Distinguishing readout failure from capability loss

Measure an organ at three interfaces:
1. deployed model + current head/adapter/router;
2. frozen backbone/representation with a newly trained diagnostic readout;
3. representation-level separability or task-specific probe.

A recovered probe score does not automatically mean the deployed organ is repaired; it indicates information may remain accessible through another readout. Report deployed performance and representation recoverability separately.

## 9. Cost vector

Every resilience result should include:
K = (compute, tokens, memory, bandwidth, latency, verifier effort, storage, healthy-work loss, unsafe-effect cost)

A method is not strictly better because it improves task success while consuming unreported recovery compute or imposing large false-quarantine costs.
