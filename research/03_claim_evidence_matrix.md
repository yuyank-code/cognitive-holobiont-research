# Claim–Evidence Matrix

This document tracks major Holobiont claims against external evidence. The treatise is a hypothesis/specification, not established fact.

| ID | Claim / hypothesis | Evidence for | Evidence against / limits | Status | Confidence | Last reviewed |
|---|---|---|---|---|---|---|
| CH-001 | Specialist neural modules can provide useful task specialization | MoE/modular literature; causal circuit work identifies compact functional circuits | Fixed parameter boundaries may not match functional boundaries; specialization can be overwritten | Strongly supported | High | 2026-09-06 |
| CH-002 | Learned/training-free latent bridges can communicate useful information between specialist models | Latent-MAS, model stitching, StateBridge/Vision Wormhole evidence | Task-specific gains do not establish semantic equivalence or universal portability | Strongly supported for bounded interoperability | High | 2026-09-06 |
| CH-003 | Latent communication can transfer genuinely novel sender-specific information to a receiver | 2026 causal audits show positive sender/example pairing effects when private sender information is required | Effects vary by model/task; large generic relay effects can lack pairing; not universal | Partially supported; task/setting dependent | High | 2026-09-06 |
| CH-004 | Shared lower-level parameters can provide a useful common representational substrate | Shared backbones, stitching/alignment, adapters | Shared structure may increase correlated errors; heterogeneous models can be interoperable without one global geometry | Strongly supported for some interoperability settings | High | 2026-09-06 |
| CH-005 | A high shared-parameter ratio can preserve useful specialization | Shared pretrained bases + LoRA/PEFT | PMLR 2026 expert-collapse evidence shows later shared multimodal training can overwrite specialization | Partially supported; specialization is fragile | Medium-high | 2026-09-06 |
| CH-006 | Continuous communication can preserve specialization with suitable control | Adaptive topology and diversity-aware debate show bounded benefits | Dense interaction accelerates convergence; single-agent multi-output can exceed MAS diversity | Plausible, conditional | High | 2026-09-06 |
| CH-007 | Hypernetworks can encode enough information to regenerate large specialist models | Hypernetworks generate target weights/adapters; Universal Hypernetwork/SHINE | No evidence for arbitrary recovery of unique capabilities after destruction | Partially supported | Medium | 2026-09-06 |
| CH-008 | Compact shadow copies can support functional specialist regeneration | PEFT/LoRA and generated adapters preserve substantial behavior | Rare/OOD capability and unique-information preservation remain unproven | Plausible hypothesis | Medium-low | 2026-09-06 |
| CH-009 | Multiple specialists can reliably detect one corrupted specialist | Ensembles, uncertainty, Byzantine filters, confidence-weighted debate | Correlated/shared priors and collusion can fool groups; abstention needed | Partially supported | Medium | 2026-09-06 |
| CH-010 | Consensus/debate can improve correctness rather than only agreement | Diversity-aware initialization + calibrated confidence improve tested debate; consensus-free debate can also work | Vanilla debate can underperform; problem drift and conformity can amplify errors | Partially supported as evidence-weighted inference, not consensus itself | High | 2026-09-06 |
| CH-011 | Distributed redundancy provides meaningful resilience under component failure | N-version experiments; self-organising circuits show functional repair | Common-mode/specification failures remain; learned knowledge recovery open | Strongly supported in bounded settings | High | 2026-09-06 |
| CH-012 | Common-mode failures can be sufficiently controlled to preserve fault tolerance | Byzantine protocols, diversity controls, adaptive topology | Shared backbone/data/memory/specification/routing/generator and dense communication correlate failures | Open / weakly supported | High | 2026-09-06 |
| CH-013 | Distributed memory can preserve system continuity through component failure | Replication/external-memory architectures; recursive memory evolution | Semantic/cognitive continuity stronger than data persistence | Plausible hypothesis | Medium-low | 2026-09-06 |
| CH-014 | The architecture can safely modify its own communication topology | Adaptive topology methods show utility | Topology is also attack/availability surface; verification unresolved | Plausible hypothesis | Medium-low | 2026-09-06 |
| CH-015 | Recursive self-rearchitecture can produce capabilities beyond fixed modular systems | Recuris supports bounded recursive memory/harness evolution; dynamic-weight systems show bounded adaptation | Core-model recursive rewrite, long-run retention, and open-ended improvement remain unproven | Partially supported in bounded form; open-ended claim speculative | Medium | 2026-09-06 |
| CH-016 | Persistent narrative state can provide functional identity continuity | Persistent memory preserves information/state | No established bridge to subjective identity/consciousness | Speculative | Low | 2026-09-06 |
| CH-017 | Architecture provides evidence relevant to machine consciousness | Cognitive architectures/global integration ideas | Coordination is not evidence of phenomenal consciousness | Speculative | Low | 2026-09-06 |
| CH-018 | Architecture is fundamentally different from existing MoE/ensemble/multi-agent systems | Potential integrated property: private functional modules + selective latent communication + distributed recovery + fault tolerance + meta-reconfiguration | Each component has precedent; single-agent multi-output is a strong negative baseline | Open / requires proof | High | 2026-09-06 |
| CH-019 | A specialist should be defined by causal functional capability rather than fixed parameter block | Causal circuit localization + parameter editability + stitching results | General organ ontology not established | Plausible | Medium | 2026-09-06 |
| CH-020 | Collective abstention/termination can improve reliability under capability overreach | Capability-aligned quitting and confidence-aware aggregation | Evaluator/grounding/domain shift remain issues | Partially supported | Medium | 2026-09-06 |

## Rules

- Every new paper should update at least one relevant claim when applicable.
- Supporting and contradictory evidence must both be recorded.
- “No evidence found” is not equivalent to “disproved.”
- Strong claims require direct experimental evidence whenever possible.
- The status may move backward when stronger contradictory evidence appears.
- Parameter reconstruction is not treated as capability regeneration without behavioral/OOD evidence.
- Multi-agent claims must be compared against compute-matched single-model multi-output/self-conditioning baselines.
