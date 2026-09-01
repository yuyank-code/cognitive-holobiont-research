# Automation Pass 08 — 2026-09-01

## Scope
Fresh search focused on latent communication, model stitching, MoE specialization/diversity, consensus under heterogeneous agents, Byzantine resilience, and recursive self-improvement. The treatise remains a hypothesis/specification.

## New evidence

### 1. Latent communication is broadening, but interoperability is the key problem
- *Beyond tokens: a unified framework for latent communication in LLM-based multi-agent systems* (arXiv, June 2026) organizes 18 representative latent-communication methods from 2024–2026 by communicated state, sender-receiver alignment, and fusion mechanism. It identifies cross-architecture alignment and latent-channel security as open problems.
- *Latent Space Communication via K-V Cache Alignment* (arXiv:2601.06123, January 2026) aligns K/V caches through adapters and reports cross-model collaboration and transfer of soft prompts. This supports high-bandwidth latent interfaces but does not by itself prove novel-information transfer.
- *The Vision Wormhole* (arXiv:2602.15382, February 2026) uses a universal visual codec as a hub-and-spoke communication port for heterogeneous VLMs, reducing pairwise alignment complexity from O(N^2) to O(N). This is directly relevant to scalable Holobiont interfaces.

Assessment: latent communication feasibility = strongly supported; scalable heterogeneous interoperability = early supporting evidence; arbitrary novel cognitive-state transfer = unresolved.

### 2. Model stitching cannot be used naively as evidence of shared cognition
- Balogh & Jelasity, AAAI 2025, *How Not to Stitch Representations to Measure Similarity*, shows task-loss-based stitching can report misleading functional similarity because the learned mapper may create out-of-distribution representations. Direct matching behaves more consistently as a similarity measure.
- 2026 invariance-aware stitching work further argues that forward compatibility can hide differences in the information invariances used by the models; forward/backward compatibility is a stronger test.

Implication: successful stitching is evidence for usable translation, not proof that two organs share the same semantics or internal computation.

### 3. Expert diversity remains fragile
- 2026 *Geometric Regularization in Mixture-of-Experts: The Disconnect Between Weights and Activations* reports that orthogonality regularization fails to reliably create weight or activation diversity and finds no significant relationship between weight and activation orthogonality.
- PMLR 332 (AAAI 2026 workshop) *Expert Collapse and Compositional Failure in Simple Multimodal MoE* finds that specialization induced in a controlled stage can be overwritten by later multimodal training, with latent organization collapsing toward modality rather than concept.

Implication: independence must be measured functionally (error correlation, activation overlap, OOD/adversarial transfer, calibration correlation), not by parameter distance.

### 4. Consensus evidence is mixed and points toward reliability-aware aggregation
- *ConSensus* (arXiv:2601.06453) reports 7.1% average gains from specialized multimodal agents plus hybrid semantic/statistical fusion on five sensing benchmarks.
- *Learning to Trust the Crowd* (arXiv:2601.07245) reports a learned multi-model consensus engine outperforming majority vote on several compact benchmarks, suggesting that agreement statistics can be useful when combined with model-specific priors and reasoning-quality features.
- *Robust Multi-Agent LLMs under Byzantine Faults* (arXiv:2605.09076) proposes self-anchored consensus with graph robustness conditions and reports suppression of Byzantine influence.
- *Opinion Consensus Formation Among Networked LLMs* (IEEE ICASSP 2026) reports convergence of opinion scores in tested text-interaction settings.
- However, these results concern agreement/performance under bounded settings; none establishes that consensus is inherently truth-seeking. They also do not eliminate common-mode errors or collusion.

Updated assessment: aggregation can improve reliability = supported; consensus = truth = unsupported.

### 5. Recursive self-improvement remains bounded
- *Hyperagents* (arXiv:2603.19461, March 2026) proposes editable meta-level self-modification where the mechanism that generates future improvements is itself editable. This is conceptually closer to recursive self-rearchitecture than ordinary self-refinement.
- A 2026 paper on self-referential introspection frames sustainable recursive improvement as requiring the system to model its own operations; this is a theoretical proposal, not evidence of open-ended capability.
- Current evidence still lacks a convincing demonstration of monotonic, open-ended architecture self-improvement with preservation of prior capabilities.

## Major revised conclusions

1. The shared-latent-space hypothesis should be replaced by a weaker and more defensible shared-interface hypothesis: private internal representations plus learned interoperability may be sufficient.
2. Model stitching is a tool for interface construction, not a reliable standalone assay of semantic equivalence.
3. Expert independence must be defined statistically/behaviorally, with explicit common-mode-failure tests.
4. The Holobiont's epistemic layer should preserve disagreement, provenance, uncertainty, and reliability history rather than simply enforce consensus.
5. Hub-and-spoke latent interfaces may offer a concrete route to O(N) rather than O(N^2) alignment, but the information bottleneck and security properties remain open.
6. The strongest unresolved regeneration question remains capability recovery after destruction, especially when the capability is absent from all surviving specialists.

## High-priority falsification experiments added

- **Novel-information latent channel test:** give sender-only facts after receiver pretraining; require receiver recovery through latent channel under matched controls that eliminate shared-data explanations.
- **Interface-vs-shared-representation ablation:** compare private representations + translator interface against a forced common latent space at matched communication bandwidth.
- **Functional-diversity stress test:** independently vary shared weights, shared data, shared memory, and shared repair generator; measure pairwise and higher-order failure correlation under IID, OOD, and adversarial inputs.
- **Consensus truth test:** construct correlated-error and colluding-agent conditions where majority is predictably wrong; compare majority vote, learned reliability aggregation, evidence-preserving aggregation, and Byzantine filters.
- **Capability-regeneration test:** destroy a specialist whose unique capability is not present in surviving modules; compare checkpoint recovery, LoRA regeneration, hypernetwork regeneration, and distributed reconstruction.
- **Recursive rearchitecture retention test:** allow architecture modification only when a held-out evaluator and capability-retention suite both pass; measure improvement, regression, and irreversible capability loss across multiple generations.

## Source links
- https://arxiv.org/abs/2606.05711
- https://arxiv.org/abs/2601.06123
- https://arxiv.org/abs/2602.15382
- https://ojs.aaai.org/index.php/AAAI/article/view/33698
- https://arxiv.org/abs/2601.06453
- https://arxiv.org/abs/2601.07245
- https://arxiv.org/abs/2605.09076
- https://arxiv.org/abs/2603.19461
- https://proceedings.mlr.press/v332/ticinovic26a.html
