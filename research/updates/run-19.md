# Cognitive Holobiont — Run 19 — 2026-09-08

## Scope
Substantive literature pass across modular AI/MoE, latent communication, distributed coordination, Byzantine reliability, hypernetworks, and recursive self-improvement. The treatise remains a hypothesis/specification, not established fact.

## 1. New evidence: specialization is an engineering problem, not an automatic consequence of MoE

Recent MoE work gives both positive and negative evidence. Path-Constrained MoE reports that shared routing structure across layers improves cross-layer consistency and robustness to routing perturbations. A 2026 Expert Collapse study finds that experimentally induced specialization can be overwritten by later multimodal training. EMO explicitly targets independent composition of expert subsets because ordinary MoE expert subsets can degrade badly when used independently.

Interpretation: specialization must be measured longitudinally and causally. A module is not an "organ" merely because routing assigns it a domain. Durable specialization requires retention under continued training, recombination, intervention, and partial failure.

## 2. Latent communication: the strongest evidence now supports conditional causal transfer, not universal latent-thought transmission

The July 2026 causal audit shows that message replacement can separate message-presence effects, other-example information, example-specific content, and additional sender value. The August 2026 follow-up audit strengthens this: when receiver-private information is genuinely required, matched-cache controls can show a large pairing effect; when it is not required, large cache effects can remain without example-specific transfer. Results also vary by architecture/projector.

Interpretation: latent communication can causally transmit sender-specific information in some regimes, but "latent channel gain" is not itself evidence of novel information transfer. Every future result must include mismatched-example, zeroed, random/moment-matched, and receiver-isolation controls.

## 3. Communication topology is now a resource allocation problem

ACL 2026 Diversity Collapse finds dense communication accelerates premature convergence. SILO-BENCH finds high communication density can coexist with failure of distributed computation, with severe degradation on high-complexity tasks as group size grows. TopoDIM shows that learned one-shot topologies can reduce communication cost while preserving or slightly improving performance.

Interpretation: topology should be treated as an adaptive control variable. The target is not maximum connectivity but maximum useful independent information transfer per unit communication and induced coupling.

## 4. Consensus is no longer the right primitive

Free-MAD demonstrates that multi-agent debate can work without forced consensus by scoring trajectories and using anti-conformity. AAAI-26 Byzantine work shows confidence-probe weighted consensus can improve reliability under extreme tested fault rates, but this is evidence for weighted fault-tolerant aggregation, not proof that agreement equals truth.

Interpretation: the Holobiont fusion layer should preserve dissent and use provenance, dependency, confidence calibration, contradiction detection, and abstention before commitment. Consensus is one possible output protocol, not the epistemic objective.

## 5. Hypernetwork regeneration: stronger scaling evidence, unchanged information-theoretic limit

SHINE and 2026 scaling-law work strengthen the case that hypernetworks can generate LoRA/adaptation parameters from context and that performance scales predictably with hypernetwork depth/width and target-model size. Code2LoRA further demonstrates repository-specific generated adapters with evolving hidden state. The Override Gap shows a major failure mode: generated knowledge can lose conflicts against strong pretrained priors unless adapter magnitude is sufficient.

Interpretation: hypernetworks are increasingly credible as parameter/adaptation generators, but capability regeneration remains a distributed-information problem. A generator that already stores the missing capability is a redundancy mechanism, not recovery from information loss. Regeneration experiments must test rare capability retention, conflict fidelity, OOD behavior, calibration, and collateral regression.

## 6. Recursive self-improvement: the credible frontier remains bounded meta-evolution

Recent work continues to separate stable meta-processes from unrestricted self-rewriting. Hyperagents proposes an editable meta-level procedure, while recent self-referential introspection work argues that sustainable recursive improvement requires useful internal models of the system being modified. These are proposals/early evidence, not proof of open-ended RSI.

Interpretation: the Holobiont should prefer reversible, validation-gated evolution of routing, memory, repair, and harness policies before considering core-model rewriting.

## 7. Mathematical revision

Define an effective independent information budget rather than raw agent count:

K_eff = effective rank / usable channel count of task-relevant, causally distinct evidence streams after accounting for dependency.

For a communication graph G_t, define a qualitative utility objective:

U = CapabilityGain - lambda_B Bandwidth - lambda_C Coupling - lambda_F JointFailure - lambda_P PrivacyRisk - lambda_O CoordinationOverhead.

The new requirement is to estimate the derivatives of U with respect to topology density, message frequency, and specialist correlation rather than assuming monotonic benefit from communication.

For regeneration, let K be capability information distributed across surviving state S and generator memory M. Recovery is bounded by I(K; S,M). Exact parameter recovery is unnecessary; behavioral regeneration requires equivalence over a specified task/OOD distribution. If I(K;S,M) is insufficient, no internal generator can recover the missing capability without external information.

## 8. Revised claim changes

- CH-001: remains Strongly supported, but durable specialist identity is only Partially supported.
- CH-003: remains Partially supported; causal sender-specific transfer is now conditional and mechanism-dependent.
- CH-006: Plausible/conditional; topology and communication rate are control variables, not monotonic resources.
- CH-007: Partially supported with stronger evidence for scalable adaptation generation; capability regeneration remains unsupported.
- CH-009/010: Partially supported; weighted/dependency-aware aggregation is better supported than consensus-as-truth.
- CH-012: remains Open; correlated failures remain the central systems bottleneck.
- CH-014: strengthened to Plausible/partially supported for adaptive topology utility, while safe autonomous topology control remains unresolved.
- CH-015: bounded recursive meta-evolution strengthened; unrestricted core self-rearchitecture remains speculative.
- CH-018: still Open; novelty requires a matched-resource full-system advantage.
- CH-021: K_eff remains a promising abstraction, not a validated universal law.
- CH-022: coupling is measurable only with triangulated metrics.
- CH-023: trajectory/topology-aware uncertainty remains promising.

## 9. New falsification priorities

F19.1: Compare durable specialist retention under continued joint training against standard MoE, Path-Constrained routing, EMO-style modular MoE, and independent models.

F19.2: Latent-transfer audit across at least three architectures using matched, mismatched-example, zeroed, random, and receiver-private-information conditions.

F19.3: Communication phase diagram: sweep topology density x bandwidth x group size x correlation; measure K_eff, useful diversity, joint failure, and task utility.

F19.4: Consensus-vs-dissent benchmark with truthful correlated evidence, collusion, useful minority specialists, and specification errors.

F19.5: Regeneration benchmark where unique specialist capability is distributed at controlled redundancy levels; destroy specialists and test OOD behavior, calibration, conflict fidelity, and rare capability recovery.

F19.6: Meta-evolution retention test across many validated generations; require improvement plus non-regression on an expanding historical suite.

## Bottom line

The Holobiont hypothesis is becoming narrower and more testable. The strongest defensible formulation is a distributed system with causally identifiable but dynamically maintained specialists, selective authenticated communication, dependency-aware evidence fusion, distributed capability traces, calibrated abstention, and bounded reversible meta-evolution. The decisive evidence is still absent: no result yet demonstrates that this complete combination produces a matched-resource advantage that cannot be decomposed into existing MoE, ensemble, latent-MAS, memory, and repair mechanisms.
