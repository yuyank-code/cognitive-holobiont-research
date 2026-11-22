# Contradictions and Open Problems — Pass 37
**Date:** 2026-11-22

## Contradictions and boundary conditions

1. **Multi-agent wins and losses coexist.** Kim et al. report large gains for centralized coordination on a parallelizable finance task and severe degradation on sequential planning. Tran & Kiela find single-agent systems match or outperform tested MAS under equal reasoning-token budgets on multi-hop reasoning. Neither supports a universal rule.
2. **More tokens can buy score without proving architecture value.** BenchAgent's EvoAgent improves pooled accuracy by about 3.05 percentage points but uses 1.27× the tokens. LLM-Debate and ChatEval spend more tokens yet underperform pooled Core. Same step limits are not the same as equal total compute.
3. **Emergence is not performance.** Riedl measures higher-order coordination and complementarity, but the group success rates reported on the minimal guessing game are similar across prompting conditions. A synergy statistic must predict external utility, not replace it.
4. **Simulation validity is not complete deployment validity.** OrchBench reports Pearson r=0.816 but Spearman p=0.103 on its small validation set; time and token usage correlations are not significant. Use it for screening, not final claims.
5. **Heterogeneity is often weaker than the Holobiont requirement.** The Google scaling study uses agents from the same architecture family, varying scale and role prompts. BenchAgent uses one GPT-4.1 backend. These do not establish persistent autonomy of distinct specialist models.
6. **Positive edge-level collaboration evidence has comparator limits.** SC-MAS improves on MAS construction baselines and has useful ablations, but its main result is not a complete comparison against a strong single-model Pareto frontier; its DAG excludes cycles.
7. **Compact fully observed tasks can punish decomposition.** The Frontiers rover benchmark finds substantial latency/token overhead without reliable aggregate decision improvement; its synthetic, prompt-defined setting does not settle tasks requiring independent sensors or private data.
8. **Reported thresholds are not laws.** The ~45% single-agent baseline pattern in Kim et al. is specific to its tasks, models, budgets and configurations. It must not be hard-coded as a universal router cutoff.

## Open questions

- Does a federation still win when a single model receives the union of all evidence and the same total compute?
- When private evidence is partitioned across organs, is the gain due to information access, parallelism, expertise, or coordination?
- Can the federation preserve unique information that best-of-K and single-model multi-output cannot recover?
- Which measurable task features predict a positive architecture choice across unseen domains?
- Does persistent organ specialization add value beyond query-conditioned model routing?
- Can a task-conditioned topology adapt without losing critical dependencies or creating correlated failure paths?
- Does measured PID synergy predict benchmark and real-task improvements after controlling for model strength and resource use?
- How do compute, token, latency, memory, bandwidth, tool and verifier budgets trade off? Which Pareto comparisons are meaningful?
- Can the same architecture-selection rule transfer across model families and genuinely different modalities?
- What is the minimum scale at which independent specialist identity becomes useful rather than coordination overhead?

## Research warning

Do not equate:
- more agents with more intelligence;
- different prompts with independent expertise;
- output disagreement with useful diversity;
- information-theoretic synergy with task-level utility;
- benchmark accuracy with fault tolerance;
- a positive raw score difference with a resource-adjusted architecture advantage.
