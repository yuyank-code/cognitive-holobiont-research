# Cognitive Holobiont Research — Pass 20
Date: 2026-09-30

## Scope
Substantive literature pass focused on whether multi-agent gains are caused by genuine coalition-level computation or by extra compute, diversity, context management, verification, or orchestration. The originating PDF remains a hypothesis/specification, not established fact.

## New evidence

### 1. Stronger negative controls: compute normalization
Tran & Kiela (2026), *Single-Agent LLMs Outperform Multi-Agent Systems on Multi-Hop Reasoning Under Equal Thinking Token Budgets*, report that when total reasoning tokens are strictly matched, single-agent systems can match or outperform multi-agent systems across Qwen3, DeepSeek-R1-Distill-Llama, and Gemini 2.5. Their information-theoretic argument uses the Data Processing Inequality and highlights API/benchmark budget artifacts.
Source: https://arxiv.org/abs/2604.02460

Implication: any Holobiont experiment that does not equalize total reasoning compute is scientifically weak. "More agents" cannot be treated as an independent causal variable when it also increases inference budget.

### 2. Important positive counterevidence: communication can create discoveries
*Scaling Discovery through Test-Time Communication* (arXiv:2609.21032, Sep. 17 2026) reports that on ARC-AGI-3, communicating teams can outperform independent parallel attempts; the reported team@k performance can match the success rate of roughly 4k independent agents, and some tasks reportedly become solvable only through team communication.
Source: https://arxiv.org/abs/2609.21032

Implication: the research cannot collapse into the claim "communication is mostly harmful." There is credible counterevidence for communication-mediated breakthrough propagation. The key unresolved question is whether this is genuine synergy from complementary private information or simply a more efficient way of reallocating/propagating test-time search.

### 3. Interaction Tax: full-solution exchange can destroy diversity
Ann, Liu & Tan (ICML 2026), *The Interaction Tax*, evaluate 11 verifier-scored optimization tasks under matched budgets. Full-solution interaction can rapidly collapse diverse proposals; independent generation preserves coverage. Their result supports conditional communication rather than maximal communication.
Source: https://arxiv.org/abs/2608.23541
Artifact: https://github.com/SummerAnn/interaction-tax

Implication: "communication" must be decomposed into message types and timing. A Holobiont should distinguish evidence, constraints, uncertainty, partial discoveries, critiques, and full candidate solutions.

### 4. SILO-BENCH strengthens the integration bottleneck
SILO-BENCH evaluates 54 configurations across 30 distributed-information tasks. Agents communicate actively and often form sensible topologies but still fail to synthesize distributed state; performance collapses on high-complexity tasks at scale.
Source: https://aclanthology.org/2026.acl-long.1354/
Artifact: https://github.com/jwyjohn/acl26-silo-bench

Implication: acquiring information and computing with it are distinct capabilities. The Holobiont benchmark must separately measure retrieval/acquisition, integration, and final decision quality.

### 5. Shared verified context is a serious alternative
DeLM uses asynchronous agents, a shared verified context, and a task queue. The authors report improvements on SWE-bench Verified and LongBench-v2 while reducing cost in their comparisons.
Source: https://arxiv.org/abs/2606.10662
Artifact: https://github.com/yuzhenmao/DeLM

Implication: private routing is not inherently necessary. The architecture space should include private channels, shared verified state, and hybrids.

### 6. Adaptive topology evidence is converging
Adaptive Graph Pruning dynamically selects both agent count and communication topology, reporting gains across six benchmarks and large token reductions in its setup. TopoDIM reports reduced token use and improved performance through one-shot topology generation. MANTA adapts topology during inference.
Sources:
- https://journals.sagepub.com/doi/10.3233/FAIA251326
- https://aclanthology.org/2026.findings-acl.207/
- https://arxiv.org/abs/2607.28527

Implication: topology should be an experimental intervention variable, not a fixed architectural assumption.

## Claim-evidence matrix update

| Claim | Status after Pass 20 | Interpretation |
|---|---|---|
| More agents intrinsically improve reasoning | Rejected/weak | Compute-normalized evidence contradicts it. |
| Communication intrinsically improves reasoning | Rejected | Positive and negative results are task/message dependent. |
| Full-solution exchange preserves useful diversity | Contradicted in tested optimization regime | Interaction Tax shows convergence/diversity loss. |
| Communication can propagate unique breakthroughs | Supported locally | ARC-AGI-3 evidence is important positive counterevidence. |
| Adaptive topology is useful | Supported locally, not causally settled | Multiple independent systems report gains. |
| Verified shared context can replace central orchestration | Supported locally | DeLM is a strong competing architecture. |
| Distributed integration is a distinct bottleneck | Supported | SILO-BENCH gives direct evidence. |
| Genuine Holobiont-level causal synergy exists beyond matched baselines | Unvalidated | No current evidence isolates this cleanly. |

## Major contradiction now requiring explicit treatment

The strongest contradiction is no longer simply "communication helps vs hurts."

It is:

**Communication can destroy diversity in some regimes while enabling breakthrough propagation in others.**

A better latent variable is therefore the *marginal value of coupling*:

\[
\Delta V_{couple}
=
V(Y\mid R, M_S, \text{couple})
-
V(Y\mid R, M_S, \text{independent})
\]

This should be estimated conditionally on:
- information novelty,
- message type,
- task dependency,
- agent correlation,
- remaining compute budget,
- current uncertainty,
- and verification availability.

## Revised mathematical target

Retain the conditional-information synergy term:

\[
\Sigma(S;Y\mid R)
=
I(Y;M_S\mid R)
-
\sum_{i\in S} I(Y;M_i\mid R)
\]

but do not interpret positive \Sigma as sufficient proof of cognitive synergy.

Add an intervention-based causal quantity:

\[
\Sigma_{causal}
=
E[U\mid do(\text{complementary information exchange})]
-
E[U\mid do(\text{matched independent search})]
\]

where U is task utility and all relevant budgets are matched.

A positive result should additionally survive:
1. ownership permutation,
2. sender ablation,
3. message randomization,
4. topology intervention,
5. compute/token matching,
6. verifier matching,
7. shared-context baseline,
8. independent multi-sample baseline,
9. noisy/adversarial-agent injection.

## Revised falsification framework

The Holobiont hypothesis should be considered falsified for a task family if, after strict budget matching, the best governed multi-agent condition cannot produce a reproducible positive causal gain over the strongest single-agent and independent-ensemble baselines when private complementary information is deliberately partitioned.

Conversely, a raw accuracy improvement is not sufficient evidence.

The strongest positive result would be:
- a task with deliberately partitioned information,
- no agent initially possessing a sufficient solution,
- positive causal synergy after controlled exchange,
- loss of the gain under ownership randomization or sender ablation,
- persistence under compute/bandwidth/verifier matching,
- and robustness to moderate agent failures.

## Architecture conclusion

The architecture is now best represented as a **staged-coupling system**:

independent exploration
→ epistemic metadata
→ novelty/need estimation
→ selective evidence or breakthrough transfer
→ verified shared context
→ independent challenge
→ integration
→ verification
→ termination

The scheduler should be allowed to choose among:
**preserve independence / ask / share evidence / share breakthrough / challenge / quarantine / integrate / terminate**.

This is preferable to treating sparse communication, private routing, or shared context as universally optimal.

## Open problems

1. How to distinguish genuine coalition synergy from efficient search allocation?
2. What message representation best preserves novelty without inducing premature convergence?
3. Can synergy be detected online before expensive communication?
4. How should compute budgets be normalized across heterogeneous agents?
5. Does breakthrough propagation remain after strict compute and information matching?
6. Can shared verified context preserve diversity rather than collapse it?
7. What topology is causally optimal under changing task dependencies?
8. How does correlated model failure affect coalition synergy?
9. Can the same scheduler resist collusion, leakage, and adversarial coordination?
10. What benchmark contains enough hidden, partitioned information to make these distinctions decisive?

## Research decision

Do not implement the full system yet.

The highest-value next step is a benchmark/protocol design that factorially crosses:
- independent vs communicating agents,
- full vs partial message visibility,
- private vs shared verified context,
- static vs adaptive topology,
- homogeneous vs heterogeneous models,
- matched vs unmatched compute,
- and ownership-preserving vs ownership-permuted private evidence.

The objective is to identify a causal region where coalition synergy is real, rather than to optimize an architecture before that region is established.
