# Cognitive Holobiont Research — Pass 37
**Date:** 2026-11-22  
**Focus:** Does a federation create measurable value beyond extra compute, parallel sampling, or better orchestration?

## Executive conclusion

This pass addresses the project's central empirical claim: a federation of autonomous, heterogeneous specialist organs should be more than a costly collection of calls. It should produce a measurable advantage through complementary expertise, partitioned information, parallel work, independent verification, continuity, or resilience.

The new evidence sharpens the answer:

**Multi-agent value is task-contingent, not monotonic in agent count.** Teams can help when subtasks are genuinely parallelizable or when agents hold complementary information. They can lose when a task is sequential, the full context already fits in one model, the single-agent baseline is strong, or handoffs fragment critical reasoning. Some work now measures collective synergy and orchestration quality, but neither metric alone proves a Holobiont-specific cognitive advantage.

The next project milestone should therefore be a controlled *federation advantage test*, not a larger organ count.

## 1. Project-specific question

The original Treatise proposes many specialist minds that distribute cognition, computation, responsibility and resilience. The key research question is whether their interaction creates value that cannot be explained by:
- more total inference compute or tokens;
- best-of-K sampling or ordinary ensembling;
- a single model with the same information and tools;
- a mixture-of-experts or learned router;
- a fixed multi-agent workflow;
- a better task decomposition or verifier.

The target is not to prove that multiple agents can coordinate in some toy environment. It is to determine when a persistent, heterogeneous federation adds *causal, reproducible, resource-adjusted value*.

## 2. New evidence

### 2.1 Towards a Science of Scaling Agent Systems — arXiv preprint

Kim et al. evaluate 180 configurations across four agentic benchmarks, five coordination architectures and three LLM families, using matched token budgets and standardized tools. Their reported results are strongly task-dependent:
- centralized coordination improves performance by 80.9% on the tested parallelizable Finance-Agent task;
- decentralized coordination improves dynamic web navigation by 9.2%;
- all tested multi-agent variants degrade sequential PlanCraft performance by 39–70%;
- independent-agent error propagation is reported at 17.2×, versus 4.4× for centralized coordination with validation bottlenecks;
- additional agents have diminishing or negative returns once the tested single-agent baseline is around 45% accuracy.

The paper's own limitations are especially important for the Holobiont: agents share the same base architecture within a model family and differ mainly by scale and role prompts; teams scale only to moderate sizes (up to nine); four benchmarks do not span the full range of long-horizon and embodied tasks. The ~45% point is an empirical pattern in these experiments, not a universal threshold. The paper's abstract and body also report slightly different cross-validated R² values (0.513 and 0.524); preserve this discrepancy rather than choosing one as definitive.

Source: https://arxiv.org/abs/2512.08296

### 2.2 Single-Agent LLMs Outperform Multi-Agent Systems on Multi-Hop Reasoning Under Equal Thinking Token Budgets — arXiv preprint

Tran and Kiela compare single-agent and multi-agent approaches across Qwen3, DeepSeek-R1-Distill-Llama and Gemini 2.5 under matched reasoning-token budgets. On their multi-hop reasoning tests, the single-agent systems match or outperform the tested multi-agent systems. Their information-theoretic argument assumes idealized context utilization; their empirical study also reports budget-control and benchmark artifacts, especially for API-based measurement.

This is a serious negative result for claims that collaboration is inherently more information-efficient. Its scope is multi-hop reasoning under the tested token budget, not every setting involving private evidence, independent tools, context overflow, parallel execution or component failure.

Source: https://arxiv.org/abs/2604.02460

### 2.3 Do More Agents Help? — BenchAgent, arXiv preprint v2

Fu et al. compare one GPT-4.1 controller with six fixed/evolving multi-agent workflows over ten benchmarks and three runs. Under a shared execution substrate and step limits, EvoAgent scores 79.70% pooled accuracy versus 76.65% for the single-agent Core; the other five multi-agent configurations score below Core. EvoAgent uses 1.27× the recorded tokens. LLM-Debate uses 1.39× tokens and is 1.96 percentage points below Core overall; ChatEval uses 4.34× tokens and is 1.71 points below Core overall, despite large task-specific gains on some benchmarks.

This is not a strict equal-token experiment: Core step limits and interfaces are shared, while realized token use is an outcome. It is also one fixed sample per benchmark, three runs, one primary backend and verifiable benchmark tasks. It is nevertheless valuable because it reports pooled accuracy, per-task regressions, token costs and retained-answer changes rather than only selected wins.

Source: https://arxiv.org/abs/2606.05670 (v2, 2026-10-09)

### 2.4 OrchBench — orchestration-plan simulation, arXiv preprint

Ren et al. isolate orchestration-plan quality from worker-model execution using task DAGs with 10–1,000 subtasks. The simulator scores task quality, makespan and token efficiency; it reports Pearson r=0.816 with real Claude Code quality, but Spearman rho=0.771 has p=0.103. The correlation table is based on a small model-level validation set, and time/token correlations are not significant. The authors also note that real resource usage is framework-dependent.

OrchBench is promising as a cheap *screening and diagnosis* tool for missing information transfers and over-decomposition. It is not yet a substitute for end-to-end evaluation, and its composite score mixes quality with efficiency choices.

Source: https://arxiv.org/abs/2607.25656

### 2.5 Emergent Coordination in Multi-Agent Language Models — ICLR 2026

Riedl introduces a partial-information-decomposition framework for measuring higher-order structure, alignment and synergy in multi-agent LLM groups. In 600 experiments across four model families, ten-agent groups play a simple guessing game without direct agent-to-agent communication, receiving only minimal group-level feedback. Persona plus Theory-of-Mind prompting produces more stable identity-linked differentiation and goal-directed complementarity than the comparison prompts.

This is important because it gives the field a way to distinguish collective structure from mere parallel execution. But the task is a minimal coordination game. The paper's project page reports similar group success rates across conditions despite different measured coordination structures. Therefore, measured emergence or synergy must not be treated as proof of better task performance or general collective intelligence.

Source: https://arxiv.org/abs/2510.05174 (ICLR 2026)

### 2.6 SC-MAS — edge-level heterogeneous collaboration, arXiv preprint

Zhao et al. model agent pairs with different collaboration strategies, jointly selecting roles, graph edges and model backbones. They report accuracy and token-cost improvements over the compared multi-agent construction baseline on MMLU, GSM8K, MATH, HumanEval and MBPP. Their ablations suggest that edge strategy and model assignment matter.

This is a useful neighboring architecture for the Holobiont's connective tissue: not every pair should communicate in the same way. However, the paper's main comparisons are against other MAS construction methods rather than a comprehensive, matched single-agent frontier. Its graph is constrained to a DAG, which excludes cycles and feedback loops. Treat it as a design candidate, not proof that heterogeneous federation beats the strongest single model.

Source: https://arxiv.org/abs/2601.09434

### 2.7 Multi-Agent Reasoning Improves Compute Efficiency — ACL 2026 Student Research Workshop

Wunderlich et al. evaluate 34 inference configurations on MMLU-Pro and BBH. Under their equal-compute comparison, debate and mixture-of-agents exceed self-consistency by 1.3 and 2.7 percentage points respectively; larger test-time budgets yield further gains in some settings.

This is a positive but bounded result: the study has two benchmarks, uses a limited set of base-model regimes, and does not establish that the gains require independent specialist minds rather than a more effective allocation of test-time computation.

Source: https://arxiv.org/abs/2605.01566

### 2.8 Compact-context counterexample — Frontiers in Robotics and AI, 2026

Sanabria's peer-reviewed study evaluates single-agent and prompt-defined multi-agent architectures on 100 synthetic Mars-rover decision scenarios, using GPT-4o and GPT-5.5 with five repeated runs. When all scenario information fits in one input, multi-agent orchestration does not reliably improve aggregate decision quality after scenario-level statistical correction, while adding substantial latency and token use. The study is limited to two backends, synthetic scenarios and prompt-defined roles rather than independently trained specialists.

It is a useful boundary condition: specialization labels do not automatically justify decomposition when the task is compact and the central model already has all relevant evidence.

Source: https://doi.org/10.3389/frobt.2026.1877762

## 3. Synthesis for the Cognitive Holobiont

The evidence supports a conditional break-even principle:

**Complementarity + useful parallelism + independent verification + resilience value must exceed communication, context-fragmentation, synchronization, reconciliation and correlated-error costs.**

The likely high-value regimes are:
- tasks with independently executable subtasks;
- tasks where different organs possess genuinely private or specialized evidence;
- tasks where independent modalities/tools provide non-duplicative observations;
- tasks where one component can verify another using an independent mechanism;
- long-running tasks where a durable specialist retains state or capability that would otherwise be lost.

The likely low-value regimes are:
- compact, fully observed tasks whose context fits one strong model;
- strict sequential chains with high dependency depth;
- teams of prompt-defined roles that share the same knowledge and failure modes;
- workflows where the final synthesizer cannot preserve or verify intermediate evidence;
- settings where additional agents only increase tokens, latency and error propagation.

The Google scaling study's 45% baseline-accuracy pattern must not be hard-coded into a router. The router should estimate task properties and confidence from held-out calibration data.

## 4. Revised architecture hypothesis

The strongest near-term design is a **task-conditioned federation**, not a permanently dense swarm.

1. **Task profiler:** estimate decomposability, dependency depth, context saturation, tool density, information partitioning, uncertainty and verifier availability.
2. **Architecture selector:** choose a single specialist/generalist, independent parallel specialists, centralized/hybrid collaboration, or a more connected topology only when evidence supports it.
3. **Specialist registry:** preserve capability cards, provenance, model lineage, domain calibration and resource profiles. Do not assume role prompts equal durable specialist identity.
4. **Evidence-preserving handoff:** transmit source-linked findings, assumptions, uncertainty, unresolved dependencies and artifact identifiers; do not rely only on compressed narrative summaries.
5. **Independent integration:** compare candidate outputs, preserve dissent, and use external or structurally independent verification where possible.
6. **Budget and safety controller:** enforce total resource limits, permissions, stop conditions and abstention.
7. **Longitudinal ledger:** record which architecture helped which task family, at what cost and with what failure modes. Use this data to improve routing, not to assert universal scaling laws.

## 5. What this pass changes

- The project should no longer treat a federation as the default execution mode for every task.
- The single-agent system is a first-class baseline and may be the correct operating mode for compact or sequential tasks.
- Parallelism, information complementarity and durable specialist capability are separate sources of potential value; measure them separately.
- A measured emergence/synergy score is not enough. It must predict externally verified task utility under intervention.
- Heterogeneity must mean distinct, measurable capability or information access—not just different role prompts, names or temperatures.
- A router that chooses one organ for a task is still compatible with the Holobiont vision; the aim is a coordinated organism, not maximum simultaneous activation.

## 6. Next decisive milestone

Build no system yet. First specify a small benchmark suite with:
- a compact task where one model should win;
- a sequential task where handoffs are risky;
- a parallel task with independent subtasks;
- a private-evidence task where each specialist sees a different source;
- a multimodal task with genuinely distinct modalities;
- a long-horizon task with state changes and tool feedback;
- a fault-injection task where one organ or communication path fails.

Compare single model, single model with multi-output/self-conditioning, best-of-K, MoE/router, homogeneous MAS, heterogeneous MAS, and the proposed task-conditioned federation. Match or report a Pareto frontier over compute, tokens, cost, latency, context bandwidth, information access, tool calls and verification budget.

The decisive result is not a higher raw score at any cost. It is a reproducible positive frontier shift or a distinct resilience/continuity benefit that simpler alternatives cannot reproduce.

## 7. Scientific status

- **Original Treatise:** proposes distributed specialist organs and expects collective advantage.
- **External evidence:** task-conditioned multi-agent benefits and harms are both documented; synergy and orchestration quality can be measured in bounded settings.
- **Inference:** selective, task-conditioned federation is more defensible than always-on dense collaboration.
- **Unresolved:** whether independent heterogeneous specialists create unique, persistent, causal collective capability under matched resources; whether this advantage survives long horizons, adversarial failures and model-family changes.

No result in this pass establishes AGI, consciousness, immortality, full regeneration or a universal superiority of multi-agent systems.
