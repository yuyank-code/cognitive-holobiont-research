# Literature Map — 2026-09-08 — Run 19

## Modular AI / MoE

- Chen et al., Path-Constrained Mixture-of-Experts (2026): shared router structure across layers improves cross-layer consistency and robustness to routing perturbations; relevant to durable specialization and path stability.
- Ticinovic & Han, Expert Collapse and Compositional Failure in Simple Multimodal MoE (PMLR, 2026): induced specialization can be overwritten by later multimodal training; direct negative evidence for assuming persistent expert identity.
- EMO: Emergent Modularity in Pretrained MoEs (2026): explicitly targets independent expert-subset use/composition, motivated by degradation of ordinary MoE when subsets are isolated.
- ZipMoE (AISTATS/PMLR 2026): theoretically grounded parameter-efficient modular building block; useful baseline for modular capacity under matched budgets.

## Latent communication

- Zhang & Emu, Do Latent Channels Actually Communicate? A Causal Audit of Latent Multi-Agent LLM (arXiv:2607.26773, 2026): controlled message replacement separates message presence, other-example information, example-specific content, and sender value.
- Cheng et al., When Does Latent Communication Pay? A Causal Audit of Relayed KV Caches in Multi-Agent LLMs (arXiv:2608.04893, 2026): matched-cache audits show genuine example-specific transfer in some settings but not others; large cache effects do not imply pairing effects.
- Liu, Beyond Tokens (2026): unified taxonomy of 18 latent communication methods across representation type, alignment, and fusion; identifies cross-architecture alignment and security as open problems.

## Multi-agent coordination / topology

- Chen et al., Diversity Collapse in Multi-Agent LLM Systems (Findings ACL 2026): dense communication and scaling can accelerate premature convergence and diversity collapse.
- SILO-BENCH (ACL 2026): active communication does not imply distributed computation; high-complexity tasks can collapse as agent count increases.
- TopoDIM (Findings ACL 2026): one-shot learned heterogeneous topologies reduce token consumption while maintaining/slightly improving task performance.
- Free-MAD (Findings ACL 2026): consensus-free debate using trajectory scoring and anti-conformity can outperform forced-consensus debate.

## Reliability / Byzantine systems

- Zheng et al., Rethinking the Reliability of Multi-agent System: A Perspective from Byzantine Fault Tolerance (AAAI 2026): confidence-probe weighted Byzantine consensus improves tested reliability under extreme fault rates; relevant as aggregation baseline, not as evidence that consensus equals truth.

## Hypernetworks / regeneration

- SHINE (2026): context-to-LoRA hypernetwork maps contexts to adapters in one pass.
- Dhankhar et al., Scaling Laws for Hypernetwork-Based Knowledge Injection (2026): predictive scaling of hypernetwork knowledge injection with depth/width/target size and OOD evaluation.
- Code2LoRA (2026): repository-specific generated adapters, including recurrent evolution over code diffs.
- Cheng et al., The Override Gap (2026): generated adapter knowledge can lose against strong pretrained priors; conflict fidelity depends on adapter magnitude.

## Recursive self-improvement

- Hyperagents (2026): editable task/meta-agent formulation in which the improvement mechanism itself can be modified; important conceptual extension but not evidence for safe open-ended RSI.
- Self-Referential Introspection in LLMs (Entropy 2026): argues sustainable recursive improvement requires useful self-modeling/introspection; theoretical/proposal-level evidence.

## Synthesis

The literature increasingly converges on a shared constraint: modularity, communication, reliability, and regeneration are coupled rather than separable. The most promising architecture therefore treats topology, evidence dependency, specialization retention, and distributed information preservation as first-class variables. The main unresolved novelty claim remains full-system matched-resource superiority.
