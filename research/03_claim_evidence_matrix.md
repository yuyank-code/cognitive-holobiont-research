# Claim–Evidence Matrix

This document tracks major Holobiont claims against external evidence. The treatise is a hypothesis/specification, not established scientific fact.

| ID | Claim / hypothesis | Evidence for | Evidence against / limits | Status | Confidence | Last reviewed |
|---|---|---|---|---|---|---|
| CH-001 | Specialist neural modules can provide useful task specialization | MoE/modular literature; causal circuit work; Path-Constrained MoE; SNNL-based disentanglement | Expert Collapse shows induced specialization can be overwritten by later shared training | Strongly supported for bounded specialization; durable identity partially supported | High | 2026-09-09 |
| CH-002 | Learned/training-free latent bridges can communicate useful information between specialist models | Latent-MAS, model stitching, StateBridge | Stitchability/interface quality is task dependent | Strongly supported for bounded interoperability | High | 2026-09-09 |
| CH-003 | Latent communication can transfer genuinely novel sender-specific information to a receiver | Two 2026 causal audits use matched/mismatched/zeroed controls and find sender/example-specific effects when receiver-private information is required | Effects are regime/model/task dependent; other-example and message-presence effects can dominate in other cells | Partially supported; conditional and mechanism-dependent | High | 2026-09-09 |
| CH-004 | Shared lower-level parameters can provide a useful common representational substrate | Shared backbones, stitching/alignment, adapters | Shared structure can increase correlated errors; heterogeneous models can interoperate without one global geometry | Strongly supported for some interoperability settings | High | 2026-09-09 |
| CH-005 | A high shared-parameter ratio can preserve useful specialization | Shared pretrained bases + LoRA/PEFT | Later joint training can overwrite specialization | Partially supported; specialization is fragile | High | 2026-09-09 |
| CH-006 | Continuous communication can preserve specialization with suitable control | Adaptive topology; diversity-aware methods | SILO-BENCH shows active communication can fail to yield distributed computation; Diversity Collapse shows dense interaction can homogenize | Plausible, conditional | High | 2026-09-09 |
| CH-007 | Hypernetworks can encode enough information to regenerate large specialist models | SHINE and other hypernetworks generate adapters/weights | No evidence for arbitrary recovery of unique capabilities after destruction | Partially supported for adaptation generation | High | 2026-09-09 |
| CH-008 | Compact shadow copies can support functional specialist regeneration | PEFT/LoRA and generated adapters preserve substantial behavior | Rare/OOD capability and unique-information preservation remain unproven | Plausible hypothesis | Medium-low | 2026-09-09 |
| CH-009 | Multiple specialists can reliably detect one corrupted specialist | Ensembles, uncertainty, Byzantine filters | Correlated/shared priors and truthful-but-misleading coalitions remain failure modes | Partially supported | Medium | 2026-09-09 |
| CH-010 | Consensus/debate can improve correctness rather than only agreement | Diversity + calibrated-confidence debate; SAC/Byzantine filtering; consensus-free debate | Vanilla consensus can preserve wrong hypotheses; consensus is not a truth criterion | Partially supported as dependency-aware/evidence-weighted inference | High | 2026-09-09 |
| CH-011 | Distributed redundancy provides meaningful resilience under component failure | N-version experiments; self-organising circuits | Common-mode/specification failures remain; learned knowledge recovery open | Strongly supported in bounded settings | High | 2026-09-09 |
| CH-012 | Common-mode failures can be sufficiently controlled to preserve fault tolerance | Byzantine protocols, diversity controls, adaptive topology | Shared data/backbone/memory/router/generator and dense communication correlate failures | Open / weakly supported | High | 2026-09-09 |
| CH-013 | Distributed memory can preserve system continuity through component failure | Replication/external-memory architectures; recursive memory evolution | Semantic/cognitive continuity stronger than data persistence | Plausible hypothesis | Medium-low | 2026-09-09 |
| CH-014 | Architecture can safely modify its own communication topology | Adaptive topology methods show utility/cost savings | Topology is an attack/availability surface; safe autonomous controller verification unresolved | Plausible / partially supported for utility, unresolved for safe autonomy | Medium | 2026-09-09 |
| CH-015 | Recursive self-rearchitecture can produce capabilities beyond fixed modular systems | Recuris supports validation-gated memory/harness evolution | Long-run retention, evaluator grounding, and unrestricted core-model rewrite remain unproven | Partially supported in bounded form; open-ended claim speculative | Medium | 2026-09-09 |
| CH-016 | Persistent narrative state can provide functional identity continuity | Persistent memory preserves information/state | No established bridge to subjective identity/consciousness | Speculative | Low | 2026-09-09 |
| CH-017 | Architecture provides evidence relevant to machine consciousness | Cognitive architectures/global integration ideas | Coordination is not evidence of phenomenal consciousness | Speculative | Low | 2026-09-09 |
| CH-018 | Architecture is fundamentally different from existing MoE/ensemble/multi-agent systems | Potential integrated property: private functional modules + selective latent communication + distributed recovery + fault tolerance + meta-reconfiguration | Every component has precedent; single-agent multi-output remains a strong negative baseline | Open / requires matched-resource proof | High | 2026-09-09 |
| CH-019 | A specialist should be defined by causal functional capability rather than fixed parameter block | Causal circuit localization + parameter editability + stitching | General organ ontology not established | Plausible | Medium | 2026-09-09 |
| CH-020 | Collective abstention/termination can improve reliability under capability overreach | Capability-aligned quitting and confidence-aware aggregation | Evaluator/grounding/domain shift remain issues | Partially supported | Medium | 2026-09-09 |
| CH-021 | Effective collective diversity is better modeled as an effective channel count than raw agent count | Information-theoretic MAS scaling work motivates K* | Task/measurement dependent and not yet a universal causal metric | Promising supporting framework | Medium-high | 2026-09-09 |
| CH-022 | Communication-induced representational coupling can be measured and controlled | Diversity Collapse, topology work, repeated-run uncertainty analyses | Metrics depend on representation; causal relation to capability requires behavioral/failure tests | Partially supported | High | 2026-09-09 |
| CH-023 | Multi-agent uncertainty must model communication paths/topology, not just final outputs | MATU explicitly models trajectories, communication paths, and topologies | Calibration under adversarial correlated failures remains open | Promising / partially supported | Medium-high | 2026-09-09 |
| CH-024 | Training-free latent alignment can provide a portable communication substrate | StateBridge reports closed-form hidden-state alignment across four models/tasks | Early evidence; limited model/task families; no proof of universal semantic compatibility | Promising / partially supported | Medium | 2026-09-09 |
| CH-025 | Distributed communication can be converted into reliable exact distributed computation by simply increasing scale | — | SILO-BENCH finds active communication but severe integration failures, including zero success on hardest tasks beyond 50 agents | Contradicted for naive scaling | High | 2026-09-09 |
| CH-026 | Byzantine-resilient filtering can suppress malicious influence | SAC reports robustness across LLMs/topologies | Robust agreement/filtering does not establish truth under correlated evidence or specification errors | Partially supported | Medium-high | 2026-09-09 |

## Rules

- Every new paper should update at least one relevant claim when applicable.
- Supporting and contradictory evidence must both be recorded.
- “No evidence found” is not equivalent to “disproved.”
- Strong claims require direct experimental evidence whenever possible.
- The status may move backward when stronger contradictory evidence appears.
- Parameter reconstruction is not treated as capability regeneration without behavioral/OOD evidence.
- Multi-agent claims must be compared against compute-matched single-model multi-output/self-conditioning baselines.
- Diversity metrics must be triangulated; no single embedding-space proxy is treated as ground truth.
- Specialization must be evaluated longitudinally under continued training and intervention, not inferred from routing alone.
- Latent-transfer claims require sender/example pairing controls and receiver-private-information conditions.
- Regeneration claims must include conflict fidelity, calibration, OOD behavior, and collateral-regression tests.
- Communication density is not accepted as a proxy for distributed computation.
