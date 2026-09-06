# Literature Map — 2026-09-07 — Run 18

## Latent communication / coupling

- Zhang & Emu, *Do Latent Channels Actually Communicate? A Causal Audit of Latent Multi-Agent LLM* (arXiv 2607.26773, 2026). Primary relevance: separates message presence, identity, example-specific content, and other-agent value using controlled substitutions. Supports conditional sender-specific transfer but rejects end-task gain as a sufficient causal test.
- Liu, *Beyond tokens: a unified framework for latent communication in LLM-based multi-agent systems* (arXiv 2606.05711, 2026). Maps 18 methods across message type, alignment, and fusion; identifies cross-architecture alignment and security as open problems.
- Liu, *BOUNDARY_SYNC: Measuring Communication-Induced Representational Coupling in Multi-Agent LLM Systems* (arXiv 2607.01600, 2026). Relevant as a proposed coupling metric and evidence that communication effects can depend on group size and modality.
- Patel, *Representational Collapse in Multi-Agent LLM Committees* (arXiv 2604.03809, 2026). Measures high rationale similarity and shows encoder choice materially affects collapse estimates.

## Diversity and scaling

- Yang et al., *Understanding Agent Scaling in LLM-Based Multi-Agent Systems via Diversity* (arXiv 2602.03794, 2026). Introduces effective channel count K* and reports strong diminishing returns for homogeneous agents, with heterogeneity continuing to help in tested settings.
- Chen et al., *Diversity Collapse in Multi-Agent LLM Systems* (Findings ACL 2026). Finds dense communication and larger groups can accelerate premature convergence and reduce semantic diversity.

## Consensus, debate, uncertainty

- Zhu et al., *Demystifying Multi-Agent Debate: The Role of Confidence and Diversity* (Findings ACL 2026). Shows diversity-aware initialization and calibrated confidence improve debate over vanilla MAD and majority vote in six reasoning benchmarks.
- Chen et al., *Every Response Counts: Quantifying Uncertainty of LLM-based Multi-Agent Systems through Tensor Decomposition* (ACL 2026). Models full reasoning trajectories and communication/topology variability rather than only final outputs.
- Verma et al., *SELENE* (EACL 2026 Industry). Selective, evidence-weighted debate improves accuracy/calibration with lower token cost in tested tasks.
- Harrasse et al., *Debate, Deliberate, Decide (D3)* (EACL 2026). Uses parallel advocacy, iterative debate, budgeted stopping, and probabilistic score-gap analysis.
- Hu et al., *Lying with Truths* (ACL 2026). Shows truthful fragments can be coordinated into misleading collective beliefs, strengthening the need for provenance/dependency analysis.

## Hypernetworks and regeneration

- Liu et al., *SHINE* (arXiv 2602.06358, 2026). Maps context to LoRA in a single pass and supports in-parameter knowledge injection.
- Dhankhar et al., *Scaling Laws for Hypernetwork-Based Knowledge Injection in LLMs* (arXiv 2607.19604, 2026). Reports predictive scaling of hypernetwork knowledge injection and OOD behavior across architecture/target scales.

## Recursive improvement

- Yu et al., *Recursive Experiential-Working Memory Evolution for Long-Horizon Agent Harnesses* (2026). Recuris uses a fixed meta-agent and validation-gated memory updates; relevant to bounded recursive harness evolution rather than unrestricted self-rewriting.

## Research interpretation

The current literature increasingly supports selective heterogeneous communication and bounded recursive evolution, but no source yet establishes the full Holobiont lifecycle. The main unresolved frontier is whether effective independent evidence can be preserved while enabling enough communication for genuine distributed computation and enough distributed redundancy for capability recovery.
