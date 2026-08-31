# Literature Map — Research Pass 2026-09-01

## Executive finding

The first focused pass strengthens several foundations of the Holobiont idea, but also exposes a central constraint: **communication, regeneration, and fault tolerance pull the architecture toward shared structure, while specialization and resistance to common-mode failure pull it toward independent structure.** Current literature does not show that this tension has been solved by a single architecture.

## 1. Latent inter-agent communication

A recent feasibility study, *Enabling Agents to Communicate Entirely in Latent Space* (2025), reports direct transmission of LLM hidden states between agents and claims gains over single-agent and text-mediated baselines. The authors frame it as a feasibility study and investigate compression while retaining performance. This is meaningful positive evidence that latent communication is technically feasible.

**Important limitation:** the result does not by itself establish that communication transfers information unavailable to the receiver. The strongest Holobiont claim requires a controlled information-theoretic intervention: matched receiver, ablated sender-derived information, randomized latent controls, and tests for mutual information / conditional information gain. Performance gain alone is insufficient.

**Current status of CH-002:** Plausible / increasingly supported.
**Current status of CH-003 (genuinely novel information):** Unresolved.

## 2. Hypernetworks and regeneration

Ha, Dai & Le's ICLR 2017 *HyperNetworks* established that one network can generate weights for another and demonstrated adaptive recurrent networks. More recent work continues to use hypernetworks to generate adaptation parameters, including HyperAdaLoRA (2025), where a hypernetwork dynamically generates LoRA/SVD parameters, and HyperNet Fields (2024), which learns trajectories of task-network weights.

This establishes **weight generation as a real technique**, but not the stronger Holobiont claim that a compact hypernetwork/shadow copy can regenerate a large specialist with high-fidelity functional identity after destruction. The information bottleneck remains decisive: if the generator does not encode sufficient task-specific information, exact recovery is impossible; if it does, the purported compression may be less dramatic than the raw parameter-count comparison suggests.

**Current status of CH-007:** Strongly supported for weight/adaptation generation in bounded settings; unsupported for unrestricted large-specialist regeneration.
**Current status of CH-008:** Plausible hypothesis; requires direct destructive-recovery experiments.

## 3. MoE as the strongest existing comparator

Shazeer et al. (ICLR 2017) established sparsely gated MoE as a practical conditional-computation architecture with very large parameter capacity at comparatively limited active compute. This means that specialization + routing + shared computation are not by themselves novel.

Therefore a Holobiont novelty claim must be formulated around properties that conventional MoE does not provide: persistent independent organ state, learned inter-organ latent communication, explicit fault isolation/repair, distributed memory/identity, and safe topology self-reconfiguration.

**Current status of CH-018:** Not established. Novelty must be demonstrated through a component-by-component comparison and ablation against modern MoE systems.

## 4. Ensembles, uncertainty, and diversity

Deep Ensembles (Lakshminarayanan et al., 2017) provide strong evidence that independently trained predictors can yield useful uncertainty estimates and improved OOD uncertainty. This supports the value of diversity and independence, but it also highlights the tension with shared structure: independence can improve epistemic diversity while increasing storage/training cost and reducing shared representations.

The Holobiont immune/consensus layer should therefore measure **error correlation and conditional diversity**, not merely the number of organs or agreement rate.

**Current status of CH-009:** Plausible / supported in general ensemble settings, but Holobiont-specific corruption detection remains unproven.

## 5. Consensus is not truth

A 2026 preprint, *The Honest Quorum Problem: Epistemic Byzantine Fault Tolerance for Agentic Infrastructure*, explicitly separates protocol-level Byzantine correctness from semantic correctness. It argues that model-sharing, common training distributions, prompts, and toolchains can produce correlated epistemic failures even among nominally independent agents.

This is highly relevant to the Holobiont. Ordinary consensus/BFT can guarantee agreement under assumptions, but agreement does not imply correctness when honest agents share systematic reasoning errors. Adding more agents helps only if their errors are sufficiently less correlated.

**Current status of CH-010:** The hypothesis that consensus automatically improves truth is contradicted/unsupported. A weaker claim—that carefully diversified, calibrated consensus can improve accuracy under measurable conditions—is plausible.

## 6. Core architectural tension

The literature reviewed in this pass suggests four competing resources:

- **Shared parameters / common substrate:** improves transfer, coordination, and potentially regeneration.
- **Independent parameters / independent training:** increases diversity and can reduce correlated errors.
- **Latent communication:** can transfer rich internal information without forcing a shared full representation, but introduces alignment and bandwidth problems.
- **Regeneration mechanisms:** require a sufficiently informative persistent representation of the organ, which can recreate a common dependency or single point of failure.

This produces a central research question: **What is the minimum shared information required for reliable communication/regeneration, and what maximum shared information can be tolerated before specialization and common-mode-failure resistance collapse?**

This should become a primary experimental axis rather than a secondary implementation detail.

## 7. Priority experiments generated by this pass

1. **Novel-information latent transfer test:** compare receiver performance with sender latent, shuffled sender latent, receiver-only latent, and matched-information controls.
2. **Regeneration information curve:** vary shadow-copy bits / hypernetwork capacity and measure recovery of task accuracy, calibration, OOD behavior, and internal representations.
3. **Correlation-aware consensus:** construct organ populations with controlled shared backbones, data overlap, initialization overlap, and training procedures; plot consensus benefit against error correlation.
4. **Common-mode attack:** corrupt shared substrate, bridge, hypernetwork, memory, and routing separately; quantify simultaneous organ failure.
5. **Holobiont-vs-MoE decomposition:** compare the proposed architecture against MoE, independent ensemble, multi-agent debate, and modular networks while matching parameter count and active FLOPs.

## Primary sources from this pass

- Du et al., *Enabling Agents to Communicate Entirely in Latent Space* (2025), arXiv:2511.09149.
- Ha, Dai & Le, *HyperNetworks* (ICLR 2017).
- Zhang et al., *HyperAdaLoRA* (2025), arXiv:2510.02630.
- Hedlin et al., *HyperNet Fields* (2024), arXiv:2412.17040.
- Shazeer et al., *Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer* (ICLR 2017), arXiv:1701.06538.
- Lakshminarayanan, Pritzel & Blundell, *Simple and Scalable Predictive Uncertainty Estimation using Deep Ensembles* (2017), arXiv:1612.01474.
- He & Yu, *The Honest Quorum Problem: Epistemic Byzantine Fault Tolerance for Agentic Infrastructure* (2026), arXiv:2607.16109.
- Muralidharan et al., *Compact Language Models via Pruning and Knowledge Distillation* (2024), arXiv:2407.14679.
