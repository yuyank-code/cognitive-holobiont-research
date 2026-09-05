# Contradictions and Adversarial Evidence

This is a first-class research artifact. Evidence that weakens, contradicts, or places limits on a Holobiont claim must be preserved rather than filtered out.

## Run 17 additions

### C-022 Stitchability does not imply shared latent geometry
- **Holobiont claim:** Specialists need a shared representational substrate to communicate.
- **Claim ID:** CH-002/CH-004
- **Evidence challenging it:** 2026 model-stitching work finds heterogeneous foundation models can be stitched with suitable deep interface training even when their representations are not globally identical.
- **Evidence supporting the original claim:** Shared backbones and aligned adapters can make interoperability efficient.
- **Current interpretation:** Interface compatibility is sufficient for some communication; a global common latent space is not established as necessary.
- **Resolution experiment:** Compare learned interface maps, forced shared latent spaces, and text communication at matched bandwidth/compute.

### C-023 Specialist identity can be overwritten by shared training
- **Holobiont claim:** Once specialists differentiate, shared learning preserves their specialization.
- **Claim ID:** CH-005
- **Evidence challenging it:** PMLR 2026 multimodal MoE experiments show specialization induced early can be overwritten by later multimodal training.
- **Evidence supporting the original claim:** MoE/PEFT methods can maintain useful task-conditional specialization in bounded settings.
- **Current interpretation:** Specialization is a dynamic state requiring monitoring and possibly explicit preservation mechanisms.
- **Resolution experiment:** Measure specialist capability half-life under increasing shared-data, shared-memory, and communication coupling.

### C-024 More agents are not necessarily more diverse than one model
- **Holobiont claim:** Multiple organs intrinsically increase cognitive diversity.
- **Claim ID:** CH-006/CH-018
- **Evidence challenging it:** ACL 2026 matched study finds single-agent multi-output can exceed MAS semantic diversity.
- **Evidence supporting the original claim:** Diverse agents can improve debate when initial hypotheses and confidence are preserved.
- **Current interpretation:** Diversity is an output of conditioning and information visibility, not a guaranteed property of architectural multiplicity.
- **Resolution experiment:** Compute-matched single-model multi-output vs independent specialists vs interacting specialists.

### C-025 Collective inference need not converge to consensus
- **Holobiont claim:** Consensus is the natural endpoint of distributed cognition.
- **Claim ID:** CH-010
- **Evidence challenging it:** Free-MAD reports gains with consensus removed; other work shows conformity and problem drift can harm multi-round debate.
- **Evidence supporting the original claim:** Confidence-weighted debate can improve correctness in tested tasks.
- **Current interpretation:** The Holobiont should preserve ranked hypotheses and dissent until a separately justified commitment/abstention step.
- **Resolution experiment:** Compare consensus, score-based trajectory aggregation, confidence fusion, anti-conformity, and abstention under correlated errors.

### C-026 Self-repair can regenerate function without regenerating learned knowledge
- **Holobiont claim:** Biological-style self-repair supports cognitive regeneration.
- **Claim ID:** CH-011/CH-007/CH-008
- **Evidence challenging it:** Self-organising digital circuits and GNCA can reroute or reconstruct computational function after damage, but their target function is encoded in the task/training dynamics rather than proving recovery of unique learned semantic knowledge.
- **Evidence supporting the original claim:** Distributed repair shows local rules can restore global function after unseen damage.
- **Current interpretation:** Repair is established at the computational-function level; unique-capability regeneration remains a separate hypothesis.
- **Resolution experiment:** Destroy a specialist whose capability is not individually present elsewhere, then test recovery against distributed-code, hypernetwork, and retraining controls.

## Run 16 additions

### C-016 Causal latent gain is not equivalent to generic latent communication
- **Holobiont claim:** Latent communication transfers novel information whenever it improves performance.
- **Claim ID:** CH-003
- **Evidence challenging it:** Two 2026 causal audits show that zeroing a cache can have a large effect while a mismatched cache has little effect in some cells; other-example messages can retain substantial gains. Therefore message dependence and sender/example pairing are distinct.
- **Evidence supporting the original claim:** The same audits find strong sender/example pairing effects when the receiver truly lacks private sender information, including replication across model scales/checkpoints in one study.
- **Current interpretation:** Genuine sender-specific transfer exists in some settings but is conditional, not an automatic property of latent channels.
- **Resolution experiment:** Preregister private-information tasks and matched/mismatched/zero/random controls across model families.

### C-017 Functional modules need not be parameter modules
- **Holobiont claim:** A cognitive organ can be isolated as a fixed model block.
- **Claim ID:** CH-001/CH-019
- **Evidence challenging it:** Causal semantic-circuit work finds compact functional mechanisms with only moderate component overlap across scales and rewiring in larger models.
- **Evidence supporting the original claim:** Modular networks, MoE experts, adapters, and circuits demonstrate useful localized specialization.
- **Current interpretation:** Organ identity should be capability/intervention based, not assumed to coincide with a static parameter partition.
- **Resolution experiment:** Track a capability circuit through training, transfer, damage, and regeneration; compare parameter and behavioral identity.

### C-018 Behavioral equivalence weakens exact checkpoint regeneration as the target
- **Holobiont claim:** Regeneration should reconstruct the original specialist weights.
- **Claim ID:** CH-007/CH-008
- **Evidence challenging it:** ACL 2026 delta-parameter editability finds substantial parameter changes can preserve tested post-trained performance.
- **Evidence supporting the original claim:** Hypernetwork and adapter generation can reproduce useful task behavior.
- **Current interpretation:** Regeneration should target a behaviorally defined equivalence class with OOD/calibration constraints, not necessarily exact weights.
- **Resolution experiment:** Destroy a specialist and compare exact restore, distillation, hypernetwork reconstruction, and distributed-code recovery on broad behavioral probes.

### C-019 Recursive dynamic weights can overfit the training distribution
- **Holobiont claim:** dynamic self-reconfiguration generalizes its gains.
- **Claim ID:** CH-015
- **Evidence challenging it:** Ouroboros reports training-distribution gains but no corresponding held-out-text improvement; gated recurrence is essential.
- **Evidence supporting the original claim:** Dynamic LoRA modulation recovers part of the loss from layer removal and adapts computation by hidden state.
- **Current interpretation:** dynamic weight generation is a bounded mechanism, not evidence for general recursive self-rearchitecture.
- **Resolution experiment:** held-out distributions, adversarial shifts, long-horizon tasks, and capability-retention tests under matched compute.

### C-020 Debate gains require preserving diversity and calibrated confidence
- **Holobiont claim:** communication/consensus itself improves collective truth.
- **Claim ID:** CH-010
- **Evidence challenging it:** Vanilla multi-agent debate can underperform majority vote; homogeneous belief updating can preserve or amplify the wrong hypothesis.
- **Evidence supporting the original claim:** Diversity-aware initialization plus confidence-modulated updates improve tested reasoning benchmarks.
- **Current interpretation:** the useful mechanism is structured epistemic diversity + calibrated evidence weighting, not consensus per se.
- **Resolution experiment:** factorial manipulation of initial diversity, confidence calibration, communication timing, and aggregation.

### C-021 Capability-aware abstention is part of resilience, not a side feature
- **Holobiont claim:** more reasoning/communication should always be preferred to refusal.
- **Claim ID:** CH-009/CH-010/CH-015
- **Evidence challenging it:** ACL 2026 work finds systematic overconfidence and futile reasoning on beyond-capability tasks; prompt-only controls are insufficient.
- **Evidence supporting the original claim:** Additional reasoning can improve solvable tasks.
- **Current interpretation:** a resilient collective needs a calibrated stop/abstain state, especially when evidence sources share uncertainty.
- **Resolution experiment:** inject shared hard/ambiguous premises and compare majority, confidence fusion, and abstention-aware protocols.

## Important recurring adversarial questions

1. Does consensus improve truth, or merely agreement?
2. Does redundancy remain useful when failures are correlated?
3. Does shared representation create communication or homogenization?
4. Can latent bridges transmit novel information rather than re-encode known information?
5. Can a compact generator contain enough information to reconstruct a large specialist?
6. Can uncertainty distinguish a faulty specialist from a valid but unusual specialist?
7. Can a malicious specialist manipulate the consensus process?
8. Does regeneration preserve function, robustness, and identity, or only approximate outputs?
9. Is Holobiont fundamentally novel, or a combination of existing MoE, ensemble, multi-agent, memory, and self-healing techniques?
10. Does recursive self-modification improve the system reliably without destructive capability drift?
