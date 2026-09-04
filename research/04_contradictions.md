# Contradictions and Adversarial Evidence

This is a first-class research artifact. Evidence that weakens, contradicts, or places limits on a Holobiont claim must be preserved rather than filtered out.

## Required record format

### [CONTRADICTION-ID] Title

- **Holobiont claim:**
- **Claim ID:**
- **Evidence challenging it:**
- **Evidence supporting the original claim:**
- **Methodological considerations:**
- **Current interpretation:**
- **What experiment would resolve the disagreement?**
- **Sources:**

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
