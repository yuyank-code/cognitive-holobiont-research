# Cognitive Holobiont Research — Pass 41
**Date:** 2026-11-26  
**Focus:** End-to-end runtime resilience: fault detection, localization, containment, recovery, and safe reintegration.

## Why this part of the Treatise is being investigated

The Treatise wants the Amygdala, Heart, Hippocampus, specialist organs and connective tissue to detect unreliable components, prevent damage from spreading, preserve useful work, repair lost capability, and keep the wider system operating. Prior passes examined Byzantine influence, communication faults, provenance-aware memory, organ independence and capability regeneration separately. This pass asks whether these pieces can form a complete operational recovery loop.

The key distinction is between **detecting a fault**, **stopping its effects**, **repairing the state it already contaminated**, and **re-establishing a trustworthy component**. A system that detects a bad organ but cannot identify downstream consumers is not fully resilient. A system that quarantines everything may be safe but unavailable. A system that retries and happens to succeed has not necessarily diagnosed or repaired the cause.

## Executive conclusion

The new literature supports several bounded pieces of an end-to-end resilience architecture:

1. Controlled fault injection can expose role-specific propagation paths that clean-task benchmarks miss.
2. Runtime telemetry and metric-driven intervention can improve task completion, but detection precision, false alarms and actual recovery vary substantially by workload.
3. Provenance-guided selective containment can preserve healthy concurrent work after an alert, but current evidence relies on a trusted runtime, a supplied origin alert and bounded threat models.
4. LLM-based diagnosis of execution traces remains weak, especially for silent semantic faults and guardrail bypass.
5. Repeated retries and self-reported error annotations do not reliably repair silent faults.
6. The aggregator, coordinator, shared memory, authority gateway and recovery controller are themselves critical components and must be fault-injected.

**Revised architecture conclusion:** the Holobiont needs a fault-aware runtime control plane with deterministic enforcement and model-assisted diagnosis—not merely an immune organ that asks other organs whether they are healthy. The control plane must itself be redundant, observable and independently testable.

No existing source demonstrates the complete Holobiont lifecycle across heterogeneous autonomous organs, shared latent communication, persistent memory, peer-assisted regeneration and recursively changing topology.

## 1. New evidence

### 1.1 Agent Error Simulator (AES) — IEEE eScience 2026, peer-reviewed conference paper

Bateman et al. introduce a transparent-proxy fault injector for planner/worker/aggregator workflows. It injects format, logic and tool-call faults at selected roles and steps. The benchmark uses a deterministic Riemann-sum task with exact numerical ground truth, four open-weight models from 2B to 32B parameters, context stress, multi-fault, compaction, scale and delayed/silent detection conditions.

Findings:
- Non-final-step format and tool-call faults recover across all four tested models, because a later refinement step re-invokes the computation tool.
- Non-final-step logic faults are recovered by Qwen2.5-Coder 32B and Gemma4 27B in this test, but propagated by Mistral 7B and Granite4 2B.
- Final-step logic faults propagate even in the larger models because no subsequent refinement step exists.
- Aggregator-level format faults yield no parseable result; aggregator-level logic injection is catastrophic for every tested model.
- The aggregator's arithmetic also degrades when annotated worker outputs grow, even if worker partial results are correct.
- Delaying or suppressing the error annotation did not change the final output in the tested conditions.

Interpretation: later recomputation can accidentally repair an earlier fault, but that is not a general diagnosis mechanism. A final aggregation node can erase all worker redundancy. The Heart/Prefrontal integration stage must not be trusted solely because it receives many organ outputs.

Evidence boundary: the task is a small, deterministic numerical integration workflow, not an open-ended cognitive federation. The aggregator is given the analytical integral in its context, which is a benchmark-specific condition. The paper's abstract and result table state 194 jobs, while one body passage says 198; the reported runs include 10 job failures and 184 completed results. Preserve this internal accounting discrepancy rather than silently choosing one number.

Paper: https://doi.org/10.1109/eScience70237.2026.00052  
Author/institution page and PDF: https://grc.iit.edu/gnosis/publications/bateman-2026-agent-error-simulator-3c7d/

### 1.2 AgentChaosBench — August 2026 arXiv preprint

Zhang et al. construct 275 sanitized traces from five heterogeneous agentic applications and ten runtime fault types, with matched no-fault traces. Faults include unavailable or slow tools, context overflow, corrupted tool outputs, misrouted delegations and guardrail bypass.

Initial zero-shot LLM diagnosis is poor:
- Local detectors up to 14B reach 13.6–19.2% top-1 fault-type accuracy.
- The tested frontier API model reaches 24.8%.
- Jointly identifying both fault type and location reaches only 8–22%.
- A matched fault-free reference helps some relative diagnoses, but guardrail bypass remains near-unsolved from a trace alone.

Limitations: five systems and five aligned inputs per condition; the paper itself calls for broader task diversity. Rule-based, few-shot and specialized attribution baselines remain future work.

Paper: https://arxiv.org/abs/2608.14680

### 1.3 Airlock — 4 November 2026 arXiv preprint

Zhan et al. combine a hierarchical permission runtime with an append-only provenance DAG. After an alert, the controller traces forward to find downstream consumers and pending effects, then uses full quarantine or a deadline-aware minimum-cut strategy to fence tainted work while preserving unaffected work.

The paper reports 1,832 testbed runs, 161 physical smart-home LLM runs and 24,266 simulation records. On its main testbed and smart-home grids, it reports no post-alert faulty actuation after fenced convergence and substantially more retained healthy work than the tested native A2A/LangGraph controls.

Critical conditions and limits:
- Airlock takes the initial faulty-origin set as given; its strongest safety result is containment **after an alert**, not proof that the system can autonomously discover every fault.
- Its threat model excludes agents that adaptively evade runtime mediation.
- The OS, site daemon, broker, coordinator and effect gateway are trusted computing base components.
- The prototype contains external effects online; it does not roll back agent memory.
- A symptom-only alert has weak precise root-cause localization without healthy contrast outputs: the true origin is first in only 37% of simulation rankings, though it appears in the top three in 97%.
- The centralized coordinator's journal ingestion saturates beyond roughly ten agents across three hosts in the reported prototype.

Interpretation: provenance plus authority switches can bound the blast radius after a sufficiently good alert. They do not solve semantic fault detection, and the control plane becomes a new concentration of trust and load.

Paper: https://arxiv.org/abs/2611.06727  
Code announced by authors: https://github.com/EdgeCitadelTeam/EdgeCitadel

### 1.4 ResonAct — September 2026 arXiv preprint

Chintada et al. propose an external streaming control plane that monitors task progress, context health, tool reliability and execution traces, then chooses targeted remediation.

Across Sales MAS and AppWorld configurations:
- Task completion improves by 4.76–10.00 percentage points.
- Detection precision ranges 70.59–82.91%; recall ranges 63.09–100%.
- Recovery among detected failures ranges 10.48–46.67%.
- Runtime overhead ranges from -0.25% to +14.12%.

The false-positive trade-off is material: in one AppWorld/Granite configuration, recall is 100% but false-positive rate is 72.97%. A reported 97.7% success rate among retries actually initiated in one Sales configuration is not the same metric as recovery over all detected failed executions.

Interpretation: selective runtime intervention is promising, but a detector that over-quarantines healthy organs can undermine availability. Recovery rate must be reported with its denominator.

Paper: https://arxiv.org/abs/2609.34701

### 1.5 Loud Failures, Quiet Failures — October 2026 arXiv preprint

Kraishan evaluates 1,920 trials across six models, three model families and 24 multi-step tool tasks. Agents recognize explicit tool errors as problems in 91.3% of trials, but plausible, well-formed wrong values in only 58.8%. They report problems in 26.8% of no-fault trials. Reasoning variants notice fewer failures than their matched instruct siblings, change plans more often, but do not improve recovery. A prompt telling agents to check each result did not improve detection.

Two fault-free runs of the same task reached the same state only 63.3% of the time, complicating attribution of a recovery to the injected fault rather than ordinary run-to-run variation.

Interpretation: error-channel visibility is not semantic correctness. The Holobiont must verify content and invariants, not only exceptions, schemas or self-reported errors.

Paper and released data/code: https://arxiv.org/abs/2610.10062  
https://github.com/obadaKraishan/brittle-agents

### 1.6 System-level reliability under operational-profile uncertainty — November 2026 preprint

Tunçtürk et al. propagate interval-valued component failure probabilities through a Bayesian failure logic model, including the voting combiner itself. In a regulated chemical-hazard extraction pipeline, three-model majority voting protects against the weakest model but does not clearly exceed the best model. A voter failure probability of 5% largely erases the advantage over the middle model.

Interpretation: component accuracy alone cannot establish system reliability. The task mix, common-cause failures and combiner reliability belong in the model.

Paper: https://arxiv.org/abs/2611.07140 (submitted for IEEE Software; preprint, not a peer-reviewed result at this pass).

### 1.7 Three-interface continual-learning diagnosis — 23 November 2026 arXiv preprint

Kim et al. distinguish deployed-head performance, recoverability under a newly trained readout, and backbone representation separability. They find that apparent forgetting can be severe at the trained head while a probe recovers much of the information still present in the backbone. Head-only tuning recovers 96–99% of the gap to joint training for replay/distillation-based methods in the tested class-incremental settings, but only about three quarters for plain sequential fine-tuning.

Implication for organ health: do not classify every output regression as lost capability. Test whether the capability remains represented but inaccessible through the current readout, adapter, router or interface before attempting expensive regeneration.

Paper: https://arxiv.org/abs/2611.30151

## 2. Cross-source synthesis: the six-stage resilience lifecycle

The sources cover complementary stages, not one complete system:

1. **Observe:** record model calls, tool calls, messages, state versions, permissions, outputs and effects.
2. **Detect:** identify deviations using deterministic invariants, statistical monitors and model-assisted semantic diagnosis.
3. **Localize:** identify the fault origin and all downstream consumers using provenance and execution dependencies.
4. **Contain:** revoke or fence only affected permissions, outputs, branches and pending effects; preserve healthy work.
5. **Recover:** choose among recomputation, retry with a changed plan, rollback/replay, alternate specialist, repair adapter, checkpoint restoration or peer-assisted reconstruction.
6. **Revalidate and rejoin:** verify repaired capability, state consistency, permissions, provenance and safety before allowing the organ or branch back into shared operation.

A successful retry is not a complete recovery. A source quarantine is not enough if its output already influenced another organ. A restored model is not safe to rejoin until its local memory and derived shared records are checked.

## 3. Proposed Holobiont architecture: Fault-Aware Recovery Control Plane

### Data plane
- Specialist organs retain local reasoning and local state.
- Every inter-organ artifact has an immutable ID, source invocation, model/version, task/session, timestamp, state version, permissions and parent dependencies.
- Every external effect passes through a site-local enforcement gateway.
- Shared memory stores lineage and revocation/supersession state.

### Control plane
- **Heart:** schedules, monitors progress and coordinates recovery, but is not the only authority that can stop an unsafe effect.
- **Amygdala:** evaluates security/integrity alerts and policy violations; it can recommend quarantine but cannot forge provenance or override deterministic permissions.
- **Hippocampus:** retains episodes and repair lessons, while the memory governance layer determines admissibility.
- **Prefrontal Cortex:** plans repair/reconfiguration and compares candidate recovery paths.
- **Local site guardians:** enforce permissions, leases, deadlines and egress fences even if the central coordinator is unavailable.

### Critical design correction
Do not put all detection, root-cause attribution, quarantine and reintegration authority inside one LLM or one Heart instance. Use deterministic enforcement at the boundary, independently monitored state, and replicated/locally enforceable control records. Model-based diagnosis can propose a cause; it should not be the only mechanism that prevents an unsafe action.

## 4. Formal measures

Let an injected fault be f and let A_f be the set of external effects or downstream state transitions causally reachable from it.

- **Detection latency:** t_D - t_f, where t_f is injection/occurrence time and t_D is first valid alert.
- **Containment latency:** t_C - t_D, where t_C is the time all relevant egress fences are confirmed.
- **Weighted post-alert blast radius:**
  B_f = Σ_{a∈A_f} w_a · 1[a commits after alert and before confirmed containment].
- **Containment effectiveness:** 1 - B_f(contained)/B_f(uncontained), with denominator and alert timing reported.
- **Healthy-work retention:** H = completed eligible unaffected work / all eligible unaffected work.
- **Localization quality:** top-1/top-k root-cause accuracy, with uncertainty and symptom-only cases separated.
- **Recovery closure:** fraction of affected downstream state, memory descendants and pending effects that are corrected, compensated or explicitly marked unsafe and prevented from reuse.
- **Reintegration quality:** restored task performance plus calibration, safety, permission, provenance and regression checks on held-out cases.
- **False-quarantine cost:** healthy work stopped, delayed or discarded due to erroneous alerts.

End-to-end safe recovery can be factored by the chain rule:
P(D ∩ C ∩ R ∩ V) = P(D)P(C|D)P(R|C,D)P(V|R,C,D).
This is not an independence assumption. It makes clear why excellent containment conditional on a perfect alert does not establish high end-to-end reliability.

## 5. Decisive experiment backlog

### Experiment A — unified fault-injection suite
Build a reproducible 3–5 organ workflow with deterministic subtask ground truth, a tool boundary, shared memory and at least one external-effect simulator. Inject format, schema-valid semantic corruption, stale state, tool timeout, wrong tool result, message misrouting, compromised aggregator, compromised coordinator, memory poisoning and late alerts.

### Experiment B — separate detection from containment
Cross:
- oracle origin alert;
- noisy detector alert;
- symptom-only alert;
- no alert;
with:
- source-only cancellation;
- full workflow halt;
- branch quarantine;
- provenance-guided selective cut;
- deterministic invariant gateway.

This separates a detector's ability from a runtime's ability to contain after it is told where to look.

### Experiment C — repair strategy comparison
Compare retry-only, retry with changed plan, recompute from trusted inputs, rollback/replay, substitute specialist, repair adapter, and full restart. Use matched recovery budgets. Count a recovery only if the final state is independently verified and downstream contaminated state is closed.

### Experiment D — common-mode and control-plane faults
Corrupt the Heart/coordinator, event journal, provenance graph, authorization root, shared memory, tool gateway and evaluator. Include network partitions, delayed journal replication, duplicate/replayed messages and concurrent alerts.

### Experiment E — silent semantic failures
Inject well-formed but wrong tool outputs and agent messages. Measure detection false positives on clean runs. A schema-valid result must not be assumed correct.

### Experiment F — rejoin and memory closure
After an organ is repaired or replaced, test whether it imports stale/poisoned memories, whether its derived outputs remain tainted, and whether revocation reaches all downstream descendants. Rejoin only after independent tests.

### Experiment G — operational profile
Evaluate across task distributions, fault frequencies, consequence weights and deadlines. Report reliability intervals rather than a single average benchmark score.

## 6. Falsification criteria

The proposed resilience control plane is not justified if any of the following holds under a representative held-out fault distribution:

- It cannot outperform retry-only or full restart on verified end-to-end recovery at comparable resource cost.
- Its false quarantines erase the healthy-work advantage of selective containment.
- Provenance gaps allow post-alert effects from known-tainted outputs.
- A coordinator or authorization-root failure disables all local safety enforcement.
- Root-cause localization remains too weak to contain without halting the entire federation.
- Restored organs reintroduce contaminated memory or fail independent revalidation.
- Gains disappear when fault injection is hidden from the detector and when realistic operational profiles are used.

## 7. Evidence status

- **Original Treatise claim:** organs can detect, isolate, repair and replace one another while the wider organism continues operating.
- **External evidence:** controlled fault injection, runtime monitoring, selective containment, provenance tracking, rollback/replay and model repair each have bounded experimental support.
- **Inference:** the strongest near-term design is a deterministic, provenance-aware runtime control plane with selective containment and model-assisted recovery planning.
- **Unresolved:** end-to-end fault detection, localization, containment, repair and rejoining across a persistent federation of heterogeneous autonomous specialists.
- **Not established:** zero downtime, universal Byzantine tolerance, self-healing from arbitrary failures, peer-assisted full regeneration, AGI, consciousness or immortality.

## 8. Source status and limitations

AES is a peer-reviewed IEEE eScience 2026 conference paper; its task is controlled numerical integration and its accounting has an internal 194/198 discrepancy. Airlock, AgentChaosBench, ResonAct, Loud Failures/Quiet Failures, the operational-profile reliability paper and the three-interface continual-learning paper are arXiv preprints at this pass. Their reported metrics are not directly comparable because tasks, fault models, recovery denominators and baselines differ.

The key negative result is not that recovery is impossible. It is that **detection, localization and recovery remain weak or conditional precisely when faults are silent, downstream, late, shared or located in the integration/control plane.**

## Next research priority

Test whether a small Holobiont-style federation can complete the entire six-stage lifecycle under controlled semantic and infrastructure faults, while retaining healthy work and avoiding a single Heart/Amygdala control-plane failure. Do not advance to larger organ populations until this smaller system can diagnose, contain, recover and rejoin reliably.
