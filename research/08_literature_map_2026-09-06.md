# Literature Map — 2026-09-06 Pass

## Latent communication / model interoperability

### Revisiting Model Stitching In the Foundation Model Era (arXiv:2603.12433)
Heterogeneous vision foundation models can be stitched reliably under suitable deep feature-matching procedures; shallow stitching and naïve objectives can fail. Supports interface-level interoperability while weakening the assumption of a single shared latent geometry.

### Beyond tokens: a unified framework for latent communication in LLM-based multi-agent systems (arXiv:2606.05711)
Organizes 18 latent-communication methods by communicated state, alignment, and fusion. Useful taxonomy and open-problem map; not itself causal evidence of novel information transfer.

### The Vision Wormhole (arXiv:2602.15382)
Uses a universal visual codec and hub-and-spoke topology for heterogeneous latent communication. Relevant to scalable interface design; still needs sender-specific information controls and robustness/security evaluation.

## Modular AI / specialization

### Expert Collapse and Compositional Failure in Simple Multimodal MoE (PMLR 332, 2026)
Shows induced modality/object specialization can be overwritten by later multimodal training. Strong evidence that specialist identity is dynamically fragile.

### Mixture of Experts with Soft Nearest Neighbor Loss (arXiv:2603.26734)
Proposes representation disentanglement to reduce expert collapse and reports more orthogonal expert weights. Useful competing approach; requires broader replication and does not establish functional independence under adversarial/common-mode perturbations.

## Collective inference / debate

### Diversity Collapse in Multi-Agent LLM Systems (Findings ACL 2026)
Dense communication and larger groups can accelerate premature convergence and reduce diversity. Direct evidence for the communication-diversity tension.

### Single-Agent Generation Surpasses Multi-Agent Systems in Semantic Diversity (Findings ACL 2026)
Under matched prompting, single-agent generation can exceed MAS in semantic diversity; multi-output single-agent generation is especially strong. Mandatory baseline for Holobiont claims about diversity.

### Demystifying Multi-Agent Debate: The Role of Confidence and Diversity (Findings ACL 2026)
Finds diversity-aware initialization and calibrated confidence improve debate relative to vanilla MAD and majority vote. Supports evidence-weighted inference rather than agreement as the key mechanism.

### Free-MAD: Consensus-Free Multi-Agent Debate (Findings ACL 2026)
Removes consensus, scores the debate trajectory, and uses anti-conformity. Supports the view that collective inference can improve without forcing agreement.

### Stay Focused: Problem Drift in Multi-Agent Debate (Findings EACL 2026)
Shows multi-turn debate can drift from the original problem, especially in subjective/generative settings. Important negative evidence for unrestricted recursive communication.

### When Identity Skews Debate (ACL 2026)
Finds identity-driven sycophancy/self-bias in MAD and proposes anonymization. Relevant to provenance-aware but identity-controlled collective inference.

## Fault tolerance / self-repair

### Rethinking the Reliability of Multi-agent System: A Perspective from Byzantine Fault Tolerance (AAAI 2026)
CP-WBFT improves reliability under tested Byzantine conditions, including extreme fault rates. Supports confidence-aware Byzantine filtering but does not establish truth recovery under correlated specification errors.

### Self-Organising Digital Circuits (arXiv:2608.02606)
Self-organizing graph circuits can reroute logic around unseen faults and report >99.99% recovery on tested soft-error regimes. Strong bounded evidence for functional self-repair; not evidence for regeneration of unique learned knowledge.

### Structured Fluctuations and the Information Dynamics of Self-Maintenance in Growing Neural Cellular Automata (arXiv:2607.12403)
Finds distributed, structured internal dynamics and increased redundancy during recovery. Mechanistically interesting for biological analogies and distributed repair, but not direct evidence for cognitive regeneration.

## Recursive improvement / memory

### Recuris (arXiv:2608.24876)
Fixed meta-agent performs validation-gated localized skill-memory updates from execution evidence; reports broad gains across long-horizon benchmarks. Strong new evidence for bounded recursive memory/harness evolution, not open-ended core-model self-rewrite.

## Biological / distributed cognition direction

The self-organising-circuit and GNCA papers provide mechanistic rather than merely metaphorical biological inspiration: local update rules can support global repair and distributed recovery. The evidence still does not justify treating biological regeneration as proof of cognitive or conscious regeneration.

## Cross-cutting synthesis

The literature is converging on a design space with four separable axes: (1) functional specialization, (2) interface interoperability, (3) epistemic aggregation, and (4) recoverability. No current source establishes that combining these axes yields a qualitatively new cognitive architecture. The strongest next tests are matched-resource comparisons and controlled destruction/recovery experiments.