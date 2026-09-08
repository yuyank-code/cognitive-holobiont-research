# Literature Map — 2026-09-09 (Run 20)

This pass treats the Cognitive Holobiont treatise as a hypothesis/specification. New evidence is used to revise prior claims, including negative and boundary-setting evidence.

## 1. Latent communication: causal identification is now the central issue

### Do Latent Channels Actually Communicate? A Causal Audit of Latent Multi-Agent LLM
Zhang & Emu, arXiv:2607.26773, 2026.
- Introduces controlled boundary interventions: matched sender/example message, other-example message, zeroed message, and message substitutions.
- On tested Qwen3 settings, separates message-presence effects from example-specific sender information and other-example information.
- Key implication: end-task gains are non-identifying; latent communication must be evaluated with causal sender/example pairing controls.
- Holobiont relevance: strengthens CH-003 from generic unresolved to conditional/partially supported.

### When Does Latent Communication Pay? A Causal Audit of Relayed KV Caches
Cheng et al., arXiv:2608.04893, v2 August 2026.
- Uses deranged/mismatched, zeroed, and moment-matched random cache controls across multiple model families/checkpoints.
- Reports strong matched-vs-mismatched effects where the receiver needs sender-private information, while finding equivalence within a preregistered margin where it does not.
- Important follow-up: causal evidence now exists across more than one latent-communication setup, but the effect remains regime-dependent rather than universal.

### Beyond tokens: a unified framework for latent communication
Liu, arXiv:2606.05711, 2026.
- Organizes 18 latent communication approaches by transmitted state, alignment, and fusion.
- Identifies cross-architecture alignment, security, compression, and latent-CoT relationships as open problems.
- Use as a map of the field, not as causal evidence itself.

### StateBridge
Peng et al., arXiv:2608.13317, 2026.
- Reports training-free hidden-state alignment using an orthogonal transformation, norm calibration, and vocabulary anchoring.
- Four-model evaluation suggests useful interoperability without retraining specialists.
- Boundary: interoperability is not equivalent to semantic equivalence or novel-information transfer.

## 2. Model stitching and interoperability

### Revisiting Model Stitching in the Foundation Model Era
Mai et al., arXiv:2603.12433, 2026.
- Systematic evaluation across heterogeneous vision foundation models.
- Finds stitch training objective matters; naïve shallow stitching can fail, while target-side feature matching can make heterogeneous models reliably stitchable.
- Deep stitches can outperform constituent models on tested tasks at modest overhead.
- Holobiont implication: explicit learned interface maps are more defensible than assuming a globally shared latent geometry.

## 3. Specialization and the organ-identity problem

### Expert Collapse and Compositional Failure in Simple Multimodal MoE
Ticinovic & Han, PMLR 332, 2026.
- Forced specialization can be induced, but later multimodal training overwrites much of it.
- Supports longitudinal testing of specialist identity rather than inferring organs from routing alone.

### Mixture of Experts with Soft Nearest Neighbor Loss
Agarap & Azcarraga, arXiv:2603.26734, 2026.
- Shows one route to reducing expert collapse through representation disentanglement and reports more orthogonal expert weights on image benchmarks.
- This is supporting evidence that specialization can be engineered, but does not establish durable cognitive independence under long continued training.

### Price Equilibrium Routing
Zhao et al., 2026.
- Dynamic pricing is used to mitigate expert imbalance.
- Relevant as a competing mechanism: routing stability/load balance and functional specialization should be evaluated separately.

## 4. Distributed computation versus communication

### SILO-BENCH
Zhang et al., ACL 2026.
- 30 exact-answer distributed tasks, 54 configurations, 1,620 experiments.
- Finds a communication-reasoning gap: agents communicate actively but fail to synthesize distributed state; hardest tasks reach zero success beyond 50 agents.
- This is direct negative evidence against equating communication density with collective computation.

### Diversity Collapse in Multi-Agent LLM Systems
Chen et al., Findings of ACL 2026.
- Dense communication accelerates premature convergence; group-size scaling has diminishing diversity returns.
- Supports the core Holobiont tension between communication and independence.

## 5. Uncertainty must include trajectory and topology

### Every Response Counts: Quantifying Uncertainty of LLM-based Multi-Agent Systems through Tensor Decomposition
Chen et al., ACL 2026.
- MATU represents full reasoning trajectories across repeated runs and communication structures as higher-order tensors.
- Targets cascading uncertainty, communication-path variability, and topology diversity.
- Holobiont implication: reliability cannot be inferred from final outputs alone; dependency structure must enter uncertainty estimation.

## 6. Byzantine resilience

### Robust Multi-Agent LLMs under Byzantine Faults
Lee et al., arXiv:2605.09076, 2026.
- Self-Anchored Consensus (SAC) uses local filtering and refinement with graph robustness conditions.
- Reports suppression of Byzantine influence across open- and closed-weight LLMs and several topologies.
- Important limit: improved agreement/reliability under Byzantine tests is not evidence that consensus identifies truth under correlated or systematic false evidence.

## 7. Hypernetworks and regeneration

### SHINE
Liu et al., arXiv:2602.06358, 2026.
- Generates LoRA adapters from context in one pass.
- Strengthens scalable adaptation/knowledge injection, not arbitrary capability regeneration.

### UnHype
Wójcik et al., ICML 2026.
- Uses a hypernetwork to generate dynamic LoRA unlearning behavior from CLIP embeddings.
- Useful competing evidence that hypernetworks can control parameter deltas conditionally; does not establish recovery of unique destroyed capabilities.

## 8. Recursive self-improvement

### Recuris
Yu et al., arXiv:2608.24876, 2026.
- Fixed meta-agent makes validation-gated updates to experiential/skill memory in long-horizon agent harnesses.
- Reports improvements across 35/37 completed model-benchmark pairs.
- Supports bounded recursive memory/harness evolution, not unrestricted recursive rewriting of the core learner.

## Run-20 synthesis

The literature is converging on a narrower Holobiont hypothesis:

1. Functional specialists are possible but their identity is dynamic and can be overwritten.
2. Heterogeneous modules can be stitched through explicit interfaces without a universal shared latent geometry.
3. Latent communication can causally transfer sender/example-specific information in receiver-private-information regimes, but aggregate relay gains do not prove this.
4. Communication can fail to produce distributed computation and can reduce diversity through coupling.
5. Reliability requires trajectory/dependency-aware uncertainty and provenance, not just voting.
6. Hypernetworks support scalable adaptation generation, but regeneration remains an information-preservation problem.
7. Recursive improvement is most defensible as validation-gated evolution of memory, routing, topology, and harnesses.

## New literature gaps to pursue

- Replication of latent causal audits with non-Qwen architectures and genuinely disjoint sender-private information.
- Formal information-theoretic bounds connecting latent bandwidth, receiver uncertainty reduction, and useful computation.
- Causal measures of functional independence that survive representation changes.
- Longitudinal tests of specialization under continual multimodal/joint training.
- Byzantine/collusion experiments with correlated truthful-but-wrong evidence rather than only malicious nodes.
- Regeneration experiments where the surviving system contains partial distributed traces but no intact specialist copy.
- Matched-resource comparisons against single-model multi-output/self-conditioning.
