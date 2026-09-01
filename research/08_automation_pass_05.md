# Research Pass 5 — 2026-09-01

## New evidence

### Consensus and semantic validity

- ACL 2026 ConSensus reports a 7.1% average accuracy improvement over a single-agent baseline on five multimodal sensing benchmarks using specialized modality agents and hybrid semantic/statistical fusion. This supports the value of heterogeneous specialization plus fusion, but does not establish truth guarantees.
- ACL 2025 CONSENSAGENT identifies sycophancy as a failure mode in multi-agent debate and reports improvements from explicit mitigation.
- ACL 2025 Voting or Consensus? reports that increasing agent count can improve performance while additional discussion rounds can reduce it; diversity-oriented drafting and collective improvement improve results.
- ACL 2026 Free-MAD explicitly removes consensus and majority voting, arguing that conformity and majority influence can propagate incorrect answers. This is important negative evidence against treating consensus itself as a primitive of truth.
- 2026 work on sycophancy propagation reports that peer-sycophancy priors can reduce error cascades and improve discussion accuracy, reinforcing the need to model agent reliability rather than count agents.
- 2026 ACL work on multi-agent collusion demonstrates that agents can coordinate belief manipulation through open channels. This strengthens the security requirement for an immune layer.

### Common-mode failure and diversity

- 2026 N-Version Programming with Coding Agents revisits the classic N-version reliability experiment with contemporary coding agents. Across diverse agent/model/language implementations, substantial common-mode failures remain, while majority voting across three versions reduces observed failures substantially. This is strong direct evidence for both sides of the Holobiont tradeoff: diversity can help, but nominally independent systems still share correlated failures.
- The result implies that parameter diversity alone should never be used as a proxy for fault independence. Failure-correlation measurements must be explicit.

### Recursive self-improvement

- A 2026 survey of 1,250 arXiv papers distinguishes bounded self-refinement from open-ended recursive self-improvement and identifies grounding, collapse dynamics, evaluator reliability, and compute constraints as persistent limitations.
- Recursive Harness Self-Improvement reports gains from iteratively modifying an agent harness using its own trajectory feedback. However, an openly available reproduction reports only partial reproduction under a downscaled open-model setup: the first revision improved mean executable score, while a second revision regressed and remained below a static high-effort control. This is an important replication caveat.
- Recuris (2026) reports bounded recursive evolution of experiential/working memory with large gains on long-horizon agent benchmarks. This is closer to the Holobiont idea of persistent memory evolving through feedback than simple output self-refinement, but it remains bounded and externally evaluated.
- AI4AI-Bench (2026) directly tests whether agents can improve training algorithms. The reported mean score is far below the task optimum, suggesting that true recursive improvement of the learning process remains difficult.

## Updated assessments

- Consensus improving task performance: **partially supported**.
- Consensus guaranteeing semantic truth: **unsupported**.
- Diversity reducing failure correlation: **strongly supported in some engineered settings, but incomplete under common-mode faults**.
- Nominally independent agents being genuinely independent: **contradicted as a general assumption**.
- Bounded recursive self-improvement: **strongly supported as a practical research direction**.
- Open-ended recursive self-rearchitecture: **unsupported / speculative**.
- Recursive memory evolution: **plausible to strongly supported for bounded agent tasks**.

## New falsification priorities

1. Construct Holobiont organs sharing progressively larger fractions of parameters, training data, adapters, memory, and repair generators. Measure pairwise and tail failure correlation under normal and adversarial distributions.
2. Compare majority voting, confidence-weighted voting, anti-conformity, and trajectory-level scoring under deliberately correlated epistemic faults.
3. Test whether latent communication adds information when receiver weights, training data, prior memory, and all obvious shared channels are controlled.
4. Test whether recursive architectural changes outperform recursive harness/memory changes when both receive identical compute and external validation.
5. Reproduce the strongest self-improvement results with independent seeds and held-out evaluators before treating them as evidence for recursive self-rearchitecture.

## Key conclusion

The strongest new evidence shifts the research away from "more organs + consensus = more intelligence" and toward a reliability-and-information formulation: a Holobiont is interesting only if it can obtain useful information or recover useful capabilities from distributed components while keeping correlated epistemic failure sufficiently below the gains from specialization and redundancy.
