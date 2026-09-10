# Literature Map — 2026-09-11

## Latent communication / model interfaces

### Zhang & Emu 2026 — Do Latent Channels Actually Communicate?
- arXiv: https://arxiv.org/abs/2607.26773
- Contribution: causal interventions at latent-message boundary; separates sender/example-specific information from message-presence and other-example effects.
- Holobiont relevance: establishes the required causal-control template for latent-transfer claims.
- Limitation: evaluated tasks/models remain bounded; does not establish universal latent semantics.

### Cheng et al. 2026 — When Does Latent Communication Pay?
- arXiv: https://arxiv.org/abs/2608.04893
- Contribution: matched, mismatched, zeroed, and moment-matched random KV controls; receiver-private-information regime sharply separates useful from irrelevant relays.
- Relevance: strongest current evidence that latent transfer can be genuinely information-bearing under the right task conditions.
- Limitation: result is conditional; not every relay benefit is sender-specific.

### Mai et al. 2026 — Revisiting Model Stitching in the Foundation Model Era
- arXiv: https://arxiv.org/abs/2603.12433
- Contribution: heterogeneous foundation models can be stitched when interface objective/depth are chosen appropriately.
- Relevance: supports private internal representations plus explicit interfaces.

## Distributed cognition / scaling

### Zhang et al. 2026 — SILO-BENCH
- ACL: https://aclanthology.org/2026.acl-long.1354/
- 1,620 experiments; active communication frequently fails to become distributed computation.
- Relevance: central negative control for Holobiont integration claims.

### When 20 Agents Fail to Sort — MAS-BENCH 2026
- ACL: https://aclanthology.org/2026.findings-acl.1698/
- Explicit distributed sorting under communication constraints; success drops sharply with scale.
- Relevance: independent evidence that simple scaling is not a solution.

### ALEM 2026
- arXiv: https://arxiv.org/abs/2606.08340
- Open-ended long-horizon coordination; current LLM agents remain weak.
- Relevance: tests beyond short benchmark-style interaction.

### Yang et al. 2026 — Understanding Agent Scaling via Diversity
- arXiv: https://arxiv.org/abs/2602.03794
- Effective channel count K*; heterogeneous groups can outperform much larger homogeneous groups.
- Relevance: supports effective independent evidence as a better variable than agent count.

### Cui et al. 2026 — Single-Agent Generation Surpasses Multi-Agent Systems in Semantic Diversity
- ACL: https://aclanthology.org/2026.findings-acl.1894/
- Single-agent multi-output can outperform MAS on semantic diversity under matched prompting.
- Relevance: mandatory negative baseline.

### When Agents Disagree: The Selection Bottleneck 2026
- https://doi.org/10.3390/app16104914
- Relevance: suggests integration/selection quality can determine whether diversity helps or hurts; independent-judge attenuation is an important limitation.

## Modularity / MoE

### Ticinovic & Han 2026 — Expert Collapse and Compositional Failure in Simple Multimodal MoE
- PMLR: https://proceedings.mlr.press/v332/ticinovic26a.html
- Relevance: induced specialization can be overwritten by later multimodal training.

### Wang, Hayou & Nalisnick 2026 — The Myth of Expert Specialization in MoEs
- arXiv: https://arxiv.org/abs/2604.09780
- Relevance: routing patterns largely reflect hidden-state geometry; expert labels are not automatically semantic organs.

## Byzantine / fault tolerance

### Lee et al. 2026 — Robust Multi-Agent LLMs under Byzantine Faults
- arXiv: https://arxiv.org/abs/2605.09076
- Relevance: decentralized filtering can suppress modeled Byzantine influence.
- Limit: does not address correlated honest error/specification error.

### Zheng et al. 2026 — Rethinking Reliability of MAS from Byzantine Fault Tolerance
- AAAI: https://ojs.aaai.org/index.php/AAAI/article/view/40806
- Relevance: confidence-probe weighted Byzantine filtering under extreme tested fault rates.

## Recursive self-improvement

### Yu et al. 2026 — Recuris
- arXiv: https://arxiv.org/abs/2608.24876
- Relevance: validation-gated working/experiential memory evolution under a fixed meta-agent.
- Limit: not unrestricted core-model self-rewriting.

### Zhang, Yuan & Zhang 2026 — Self-Referential Introspection
- Entropy: https://www.mdpi.com/1099-4300/28/9/951
- Relevance: proposes self-modeling/introspection as a threshold for sustainable RSI.
- Status: conceptual/theoretical; not evidence of open-ended RSI.
