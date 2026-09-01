# Research Log

## 2026-09-01 — Repository initialization

- Dedicated repository created by the user.
- Research mandate established as a long-horizon, adversarial, evidence-driven investigation.
- Treatise designated as the originating hypothesis/specification.
- Master index created.
- Research questions framework created.
- Claim–evidence matrix initialized.
- Contradiction log initialized.
- Open-problems register initialized.
- Falsification framework initialized.

### 2026-09-01 — Prior substantive literature passes

- Established the initial evidence base across latent communication, hypernetworks, MoE, ensembles, consensus/BFT, model compression, self-healing, and recursive self-improvement.
- Key recurring conclusions: latent communication is feasible but novel-information transfer is unresolved; hypernetworks generate weights/adapters but full specialist regeneration is unproven; MoE is a major baseline; diversity must be measured functionally; consensus is not equivalent to truth; shared structure creates a central common-mode-failure tradeoff; unrestricted self-rearchitecture remains speculative.
- Earlier passes also identified modular self-healing as a baseline and distributed recovery of unique capabilities as a potentially distinctive Holobiont test.

### 2026-09-01 — Automation pass 08: latent interfaces, functional diversity, consensus, and recursive improvement

- A 2026 survey organizes 18 latent-communication methods across embeddings, hidden states, KV caches, alignment, and fusion. This confirms latent communication is becoming a distinct research area and identifies cross-architecture alignment and latent-channel security as open problems.
- K-V cache alignment work demonstrates high-bandwidth inter-model communication and soft-prompt skill transfer without changing the underlying pretrained parameters. This strengthens the case for a learned shared interface, not a shared internal representation.
- The Vision Wormhole introduces a hub-and-spoke latent interface for heterogeneous VLMs and reports O(N) rather than O(N^2) alignment complexity. This is directly relevant to scalable Holobiont communication.
- AAAI 2025 work shows task-loss-based model stitching can be a misleading measure of representational similarity; 2026 invariance-aware work further argues that forward compatibility can hide different information invariances. Successful stitching must therefore be treated as interface evidence, not semantic-equivalence evidence.
- 2026 MoE studies find that weight-space diversity does not reliably create activation diversity and that multimodal training can overwrite previously induced specialization. Functional independence must therefore be measured behaviorally and under stress.
- New multi-agent results show that aggregation can improve performance: ConSensus reports 7.1% average gains, and a learned consensus engine outperforms majority vote on several compact benchmarks. Byzantine-resilient protocols also show promise. These results support reliability-aware aggregation, but not the claim that consensus is inherently truth-seeking.
- Hyperagents and related self-referential work show that the meta-level improvement mechanism itself can be made editable. This advances the technical plausibility of recursive self-modification, but there is still no strong evidence for safe, monotonic, open-ended architecture self-reconfiguration with retention of prior capabilities.

### Automation-pass-08 conclusions

1. Replace the strong shared-latent-space hypothesis with a weaker shared-interface hypothesis: private internal representations plus learned translation may preserve specialization while enabling communication.
2. Model stitching is not a standalone test of shared cognition; invariance-aware and bidirectional tests are needed.
3. Define organ independence by failure statistics and functional behavior, not weight distance.
4. Treat the epistemic layer as reliability/evidence management rather than consensus enforcement; disagreement and provenance should be retained.
5. Hub-and-spoke latent interfaces are a concrete candidate for scalable communication, but information bottleneck, security, and novelty-of-information remain unresolved.
6. The most demanding regeneration test remains recovery of a capability that is absent from all surviving components.

### Current next priorities

1. Formalize a shared-interface vs shared-representation benchmark at matched communication bandwidth.
2. Run causal novel-information tests for latent communication with post-training sender-only facts and matched controls.
3. Build a common-mode-failure benchmark varying shared weights, data, memory, routing, and repair generators independently.
4. Compare majority, learned reliability aggregation, evidence-preserving aggregation, and Byzantine filters under correlated/colluding errors.
5. Establish information-theoretic lower bounds for regenerating specialists and measure loss of rare/OOD capabilities.
6. Test distributed capability recovery after specialist destruction against checkpoint, adapter, and hypernetwork baselines.
7. Reproduce recursive self-modification results using held-out evaluators and capability-retention suites.
8. Continue literature expansion before implementation; no architecture should be treated as validated merely because its components have individually demonstrated feasibility.
