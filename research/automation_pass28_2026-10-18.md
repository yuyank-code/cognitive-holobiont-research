# Cognitive Holobiont Research — Pass 28
**Date:** 2026-10-18

## Executive result

This pass adds a quantitative lens for distinguishing nominal agent count from independent evidence, a methodological correction for evaluating persistent memory, and positive but bounded evidence that protocol selection affects system behavior.

The main conclusion is not that multi-agent systems or memory are generally ineffective. Their value is easy to mismeasure unless the evaluation distinguishes independent evidence, answer diversity, verified task utility, temporal state reuse, and total system cost. The Treatise/PDF remains a hypothesis/specification; no implementation decision is justified by this evidence alone.

## 1. Effective team size: useful diagnostic, not universal law

Bertalanič and Fortuna's 2026 preprint, The Ringelmann Effect in Multi-Agent LLM Systems: A Scaling Law for Effective Team Size, analyzes 44 model/task/condition cells, team sizes up to 30, and core tasks MMLU-Hard, GSM-Hard, and GPQA. The study compares debate, self-correction, shuffled-message placebo, and selected heterogeneous-team and sparse-communication conditions. It reports that a two-parameter curve fits the tested profiles well and that parameters from teams of at most five predict larger-team profiles within the evaluated settings. In its tested configurations, dense peer interaction can reduce effective diversity, while selected heterogeneous compositions reduce the fitted redundancy parameter.

Sources:
- https://arxiv.org/abs/2606.02646
- https://arxiv.org/html/2606.02646

The proposed model is:

\[
N_{\mathrm{eff}}(N)=\frac{N}{1+(N-1)\rho_N},\qquad
\rho_N=cN^{-\beta},
\]

and therefore

\[
R(N)=\frac{N_{\mathrm{eff}}(N)}{N}
=\frac{1}{1+c(N-1)N^{-\beta}}.
\]

The model uses a variance-matching effective-team-size proxy. The exponent classifies fitted behavior as a hard ceiling near beta = 0, sublinear growth for 0 < beta < 1, and linear growth at or above beta = 1. These are model-dependent regimes, not established universal scaling laws for agentic systems.

### Critical measurement distinction

The paper distinguishes answer-space diversity from correctness dependence. Its entropy-derived answer count, 2^H(A), is not a direct count of useful independent evidence. On free-form arithmetic, distinct wrong numeric answers can increase entropy while correctness remains highly correlated. The authors explicitly identify this limitation.

Therefore, do not collapse these quantities into one score:
- answer diversity;
- dependence among correctness outcomes;
- decisive or complementary information recovered;
- independently verified task utility;
- calibrated uncertainty.

A team can produce many distinct wrong answers, or reach agreement because several agents share a faulty premise. Neither diversity nor consensus alone identifies the better collective.

### Scope limits

The core sweep intentionally uses homogeneous, role-symmetric, fully connected debate to isolate conformity. It does not establish scaling behavior for tool-using teams, asymmetric specialists, long-horizon planning, creative generation, multimodal tasks, or production protocol routers. Small-team extrapolation is not cross-domain validation. The authors also report no multiple-comparison correction for the reported pre-registered contrasts.

### Citation-chain comparison

The scaling-law preprint complements, rather than overturns, earlier conditional-effectiveness work:

- Revisiting Multi-Agent Debate as Test-Time Scaling compares debate with self-refinement and self-consistency at matched generation counts. Debate does not consistently win across task difficulty; benefits are clearer on some difficult AIME/MATH settings. https://arxiv.org/abs/2505.22960
- Talk Isn't Always Cheap reports both gains and regressions across CommonSenseQA, MMLU, and GSM8K, including large decreases for some model/task combinations. https://arxiv.org/abs/2509.05396
- Towards a Science of Scaling Agent Systems finds strong task dependence across a broader set of configurations; aggregate effects can conceal positive and negative task-specific effects. https://arxiv.org/abs/2512.08296

These are not direct replications: tasks, models, budgets, and interaction protocols differ. Together they support conditionality, not a blanket anti-MAS conclusion.

## 2. Persistent memory: the benchmark must allow memory to matter

Son et al.'s preprint Persistent Memory in Multi-Agent LLM Inference: What It Costs, What It Buys, and When You Can Tell (posted 2026-10-06) separates agent decomposition from the claim that persistent trace recall improves accuracy.

Sources:
- https://arxiv.org/abs/2610.07782
- https://arxiv.org/html/2610.07782

In one three-tier, six-node architecture, agent decomposition reduced peak per-call KV-cache use relative to the evaluated single-pass and retrieval-augmented baselines. In a separate persistent-recall ablation across eight dataset pairs at n=100 per arm, the reported accuracy difference was +0.015 with 95% CI [-0.011, +0.046], while peak KV cost rose by +0.368 MiB with 95% CI [+0.167, +0.590].

The authors argue that independent single-question benchmarks often provide no useful cross-item state to retrieve. They explicitly do not claim persistent recall is ineffective in general; they regard efficacy outside this regime as untested. They also identify four ablation hazards: the component may not execute, runs may retrieve their own earlier answers, arms may differ in more than the intended variable, and uncertainty may exceed the claimed effect. Some comparisons use only two to four replicates, and the study covers one system/team.

### Evaluation implications

A memory experiment should:
1. Assert in machine-readable summaries that write and read paths executed and relevant retrievals occurred.
2. Use genuine repeated entities, evolving facts, and later decisions that can benefit from earlier authorized information.
3. Preserve within-run history while preventing cross-arm contamination.
4. Vary only the intended memory operation; compare serialized requests.
5. Counterbalance run order and report paired effects plus between-run variability.
6. Measure valid retention, stale-memory rejection, retraction propagation, benign false rejection, and downstream action correctness separately.
7. Report memory footprint, context growth, tool calls, latency, and total cost.

This refines prior temporal-memory work: stale-state validity and cross-session utility are separate questions. A memory can retrieve a fact accurately but still be inadmissible; a well-governed memory tier can also have no measurable benefit on a benchmark with no useful reusable state.

## 3. Adaptive protocol choice: positive, scenario-specific evidence

ProtocolBench: Which LLM MultiAgent Protocol to Choose? (ICML 2026, arXiv:2510.17149) evaluates task success, end-to-end latency, message/byte overhead, and failure robustness. The author-hosted publication record reports up to 36.5% completion-time variation across protocols in its Streaming Queue scenario, a 3.48-second mean latency difference, and up to 18.1% lower Fail-Storm recovery time for ProtocolRouter compared with the best fixed-protocol baseline in the reported setup.

Sources:
- https://arxiv.org/abs/2510.17149
- https://www.hongyidu.ai/papers/protocolbench
- https://github.com/ulab-uiuc/AgentProtocols

This supports protocol choice as a consequential variable and adaptive routing as a testable mechanism. It does not establish universal benefit, negligible router overhead, or Holobiont-specific synergy. Compare protocol selection, topology selection, and message selection under the same total budget.

## 4. Updated claim assessment

| Claim | Pass 28 assessment |
|---|---|
| Nominal agent count measures independent evidence | Rejected as a default assumption; dependence-adjusted proxies are useful but assumption-dependent. |
| Dense debate always increases collective capability | Contradicted as a general rule; conformity and redundancy can rise. |
| High answer diversity means high useful diversity | Rejected; distinct wrong answers can inflate entropy. |
| Heterogeneity can reduce correlated outputs | Supported in selected tested settings; cross-domain utility remains open. |
| Adaptive protocol choice can improve latency/recovery | Supported in ProtocolBench's tested scenarios; generalization and router cost remain open. |
| Persistent memory is ineffective | Not supported; the observed null is limited by the benchmark regime. |
| Agent decomposition and persistent memory are the same benefit | Contradicted; peak working set and persistent recall are distinct. |
| Effective-team-size fit proves causal synergy | Rejected; fit quality is not a causal task-utility estimate. |
| Holobiont-specific synergy beats strongest feasible alternatives | Still unvalidated. |

## 5. Mathematical update

Keep at least three measures separate:

\[
D_{\mathrm{ans}}=2^{H(A)},\qquad
N_{\mathrm{eff}}^{\mathrm{corr}}=
\frac{N}{1+(N-1)\rho_{\mathrm{corr}}},\qquad
\Delta U=U_{\mathrm{intervention}}-U_{\mathrm{control}}.
\]

The first measures answer diversity, the second is a dependence proxy under its assumptions, and the third is the measured task-utility effect. For heterogeneous graphs, estimate dependence clusters or covariance structure rather than assuming a single exchangeable correlation. Shared item difficulty can also inflate observed correctness correlation, so estimate within-item social dependence after conditioning on pre-interaction performance or a separate difficulty estimate when feasible.

For a communication or protocol intervention e:

\[
\Delta V(e\mid k,B)=
\mathbb{E}[U\mid do(e),k,B]
-\mathbb{E}[U\mid do(e_0),k,B]-C(e),
\]

where k is task family, B fixes budgets and information access, and e0 is a pre-registered control. Privacy and authorization remain hard constraints, not costs that can be outweighed by utility.

For memory, estimate:

\[
\Delta U_{\mathrm{mem}}=
\mathbb{E}[U\mid do(M=1),\mathcal{H}]
-\mathbb{E}[U\mid do(M=0),\mathcal{H}],
\]

where H specifies the prior-history regime. The benchmark must establish that a relevant prior record exists, retrieval can occur, and a later decision can use it. Otherwise the experiment may estimate a null in a regime where memory has no opportunity to act.

## 6. Falsification agenda

### Scaling pilot
For each task family, compare N=1, 2, 3, 5; estimate answer diversity and correctness dependence; then test held-out sizes such as N=10, 15, 30. High in-sample R² is insufficient. Test held-out task families, backbones, heterogeneous teams, tool-grounded tasks, and role-asymmetric workflows. Include independent sampling, self-correction, shuffled-message placebo, and debate at matched generation and message budgets.

### Protocol intervention
Randomize among fixed protocols and a learned router. Match generation, context, tool, verifier, latency, and monetary budgets as closely as possible. Measure success, recovery time, failure containment, privacy leakage, and router overhead. Include deliberately wrong routing to measure regret and fallback behavior.

### Memory identifiability
Use evolving multi-session tasks where earlier authorized facts can improve later decisions. Verify read/write execution, counterbalance order, preserve within-run history, isolate experimental arms, and inject state changes. Measure correct updates, stale-action rate, invalidation lag, valid-minority retention, and downstream action correctness.

### Holobiont-specific falsification
Compare single-agent multi-output/self-conditioning, independent heterogeneous ensembles, conventional debate/Mixture-of-Agents, fixed-protocol workflows, adaptive protocol/topology routing, governed shared context/task queues, and independent proposals plus selection. Use ownership swaps, agent ablations, message substitution, edge removal/delay/corruption, fault injection, held-out task families, and independent outcome verification. A positive synergy claim requires reproducible net gains after matching information access, compute, tools, memory, verification, and privacy constraints.

## 7. Open problems

1. Does correctness-based effective team size predict utility on asymmetric, tool-using, long-horizon tasks?
2. Can scaling parameters generalize across task families rather than only team sizes within one regime?
3. How should dependence be modeled for shared tools, retrieval, hypernetworks, and common-mode failures?
4. Can useful minority information survive consensus pressure without admitting unsupported claims?
5. Which memory benchmarks permit genuine cross-session benefit and clean paired comparisons?
6. Can protocol routers reduce failure recovery after charging their own inference, routing, and verification costs?
7. Can one controller jointly choose communication, recipient, protocol, memory admission, verification, and stopping without becoming a common-mode failure point?
8. Does Holobiont-specific synergy survive the strongest feasible single-agent, ensemble, and adaptive-workflow controls?

## Research decision

Continue evidence collection and formalization; defer implementation. The best current direction remains a task-conditioned, evidence-governed collective with independent initial proposals, selective elicitation, dependency-aware evidence, versioned memory, protocol choice, independent verification, and explicit stopping. Each mechanism must be justified by its own causal effect. The combined architecture remains a hypothesis.
