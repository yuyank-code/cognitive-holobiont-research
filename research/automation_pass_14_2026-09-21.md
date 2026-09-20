# Automation Pass 14 — 2026-09-21

## Scope
Fresh pass on distributed coordination, adaptive topology, epistemic independence, fault tolerance, and the information-market hypothesis. The treatise remains a hypothesis/specification, not established fact.

## New evidence

### 1. Communication-reasoning gap remains the dominant negative result
SILO-Bench evaluates 30 algorithmic tasks, 54 configurations, and 1,620 experiments. Agents often acquire sufficient distributed information and communicate actively, yet fail at the integration/reasoning stage; coordination overhead grows with scale. This is direct evidence against the assumption that communication + specialization automatically yields distributed computation.
Source: Zhang et al., “Silo-Bench: A Scalable Environment for Evaluating Distributed Coordination in Multi-Agent LLM Systems,” arXiv:2603.01045 (2026). https://arxiv.org/abs/2603.01045
Evidence: Strongly supported for the tested LLM-agent settings.

### 2. Adaptive topology is credible, but topology alone is not the missing computation operator
RAPS frames LLM-agent coordination as dynamic ad-hoc networking and uses intent-based publish/subscribe, reactive subscriptions, and Bayesian reputation. It reports improved adaptability/scalability/robustness across five benchmarks. This supports dynamic sparse connectivity and reputation, but does not establish positive coalition synergy from privately partitioned information.
Source: Li et al., “Towards Adaptive, Scalable, and Robust Coordination of LLM Agents,” arXiv:2602.08009 (2026). https://arxiv.org/abs/2602.08009
Evidence: Partially supported for adaptive coordination mechanisms.

### 3. Structural coupling can destroy epistemic independence
Representational-collapse experiments report high rationale similarity in nominally separate committees; diversity-collapse work finds dense communication accelerates premature convergence and larger groups have diminishing diversity returns. This reinforces that interaction itself changes the effective independence of specialists.
Sources: Patel, “Representational Collapse in Multi-Agent LLM Committees,” arXiv:2604.03809 (2026), https://arxiv.org/abs/2604.03809 ; Chen et al., “Diversity Collapse in Multi-Agent LLM Systems,” arXiv:2604.18005 (2026), https://arxiv.org/abs/2604.18005
Evidence: Partially-to-strongly supported, with task/embedding dependence.

### 4. Fault tolerance requires relevance filtering, not raw consensus
Prior fault-tolerant MARL work shows agents need to select correct and relevant peer information under noisy or malicious observations. This is consistent with the Holobiont requirement for provenance, reputation, relevance, and selective integration rather than majority agreement alone.
Source: “Attention-based Fault-tolerant Approach for Multi-Agent Reinforcement Learning,” arXiv:1910.02240. https://arxiv.org/abs/1910.02240
Evidence: Established in the narrower MARL fault-tolerance setting; transfer to LLM cognition remains partial.

## Updated synthesis

The strongest architecture is no longer a generic communicating ensemble. It is a **selective distributed-information system**:

private heterogeneous specialists
→ capability-aware discovery
→ explicit information requests/offers
→ adaptive sparse topology
→ provenance/reputation + integrity
→ conditional integration
→ independent verification
→ task anchoring + termination
→ governed distributed memory
→ bounded repair
→ validation-gated reconfiguration

The missing scientific operator is now more precisely defined as **epistemic coordination**: selecting which private state must be acquired, from whom, in what representation, and when, such that the resulting coalition computes a function that cannot be reproduced by a matched centralized baseline at equal information/compute/bandwidth budgets.

## Mathematical refinement

For agent i with private state Z_i and receiver state R, define request value for message M_i as:

V_i = I(Y; M_i | R, M_{-i}) - λ_b B(M_i) - λ_t T_i - λ_c C_i - λ_f F_i

where B is bandwidth/representation cost, T latency, C coupling cost, and F estimated correlated-failure/security exposure. The previous information-market objective should therefore be extended from raw information utility to **risk-adjusted conditional information utility**.

For a coalition S, define synergy relative to a matched baseline B0 as:

Ω(S) = U(S) - U(B0 | matched compute, memory, bandwidth, verification)

A strong Holobiont claim requires Ω(S) > 0 on tasks with deliberately partitioned private information, while maintaining the advantage under agent dropout, topology perturbation, message corruption, and evaluator changes. Merely increasing accuracy by adding compute or tokens does not count.

A useful additional independence statistic is:

D_eff(S) = rank_eff(C_Z) / |S|

where C_Z is a cross-agent representation/decision correlation matrix. D_eff is not sufficient to establish epistemic independence, but it can diagnose collapse and should be paired with causal private-information ablations.

## Contradictions / cautions

1. Adaptive networking can improve coordination without proving collective computation; topology gains must not be conflated with Holobiont novelty.
2. Embedding-based diversity metrics are proxy-dependent. High or low cosine similarity does not by itself establish independent knowledge.
3. Fault-tolerant consensus can preserve agreement while preserving a shared wrong belief; correctness requires external or independent verification.
4. LLM-agent benchmark gains may arise from decomposition, extra sampling, tool access, or larger aggregate compute rather than distributed cognition.

## New falsification tests

- **Private-information swap:** permute which specialist owns each fact while keeping prompts/models fixed. A genuine information-acquisition mechanism must track ownership.
- **Counterfactual sender ablation:** replace a sender message with a distribution-matched message that removes example-specific information. Measure causal performance loss.
- **Compute/bandwidth matched central baseline:** give a centralized system equivalent total tokens, model FLOPs, retrieved evidence, and verification calls.
- **Topology perturbation:** randomly rewire or drop edges after planning. Robust benefit should degrade gracefully rather than collapse catastrophically.
- **Correlation stress test:** initialize specialists identically, then vary role prompts, data, models, and private observations to quantify which factor creates useful independence.
- **Byzantine/private misinformation test:** inject one or more plausible but false specialist reports and measure whether provenance/reputation/verifier mechanisms prevent collective degradation.

## Open problems after Pass 14

1. Can epistemic coordination produce positive coalition synergy after all resource matching?
2. Can the system estimate marginal information value without already solving the target task?
3. What representation is sufficient for cross-model transfer while preserving provenance and causal attribution?
4. How can epistemic independence be maintained dynamically without preventing useful collaboration?
5. Can repair preserve rare private capabilities without causing homogenization?
6. What is the minimum verification budget required for safe adaptive topology?

## Current evidence status

- Latent communication: Strongly supported as a mechanism; universal interoperability unsupported.
- Adaptive topology: Partially supported.
- Information-market routing: Plausible, increasingly supported mechanistically, not yet causally validated as a source of superadditive cognition.
- Distributed computation: Unresolved and remains the central falsification target.
- Resilience through independent specialists: Plausible, conditional on demonstrated independence and fault isolation.
- Regeneration of unique lost knowledge: Unsupported unless information survives somewhere in the system.

## Sources

1. Zhang et al. (2026), Silo-Bench — https://arxiv.org/abs/2603.01045
2. Li et al. (2026), RAPS / adaptive ad-hoc LLM coordination — https://arxiv.org/abs/2602.08009
3. Patel (2026), Representational Collapse in Multi-Agent LLM Committees — https://arxiv.org/abs/2604.03809
4. Chen et al. (2026), Diversity Collapse in Multi-Agent LLM Systems — https://arxiv.org/abs/2604.18005
5. Attention-based Fault-tolerant MARL — https://arxiv.org/abs/1910.02240
