# Source Ledger — Pass 37
**Date:** 2026-11-22

## 1. Kim et al. — Towards a Science of Scaling Agent Systems
- Status: arXiv preprint; submitted 9 December 2025.
- URL: https://arxiv.org/abs/2512.08296
- Scope: 180 configurations, four agentic benchmarks, five architectures, three LLM families, matched token budgets.
- Use: task-dependent coordination, sequential-task degradation, parallel-task gains, error amplification.
- Limits: model families share base architecture within family; mostly scale/role-prompt heterogeneity; up to nine agents; four benchmarks. Abstract/body R² discrepancy (0.513/0.524); 87% architecture selection prediction is not a universal unseen-domain guarantee.

## 2. Tran & Kiela — Single-Agent LLMs Outperform Multi-Agent Systems on Multi-Hop Reasoning Under Equal Thinking Token Budgets
- Status: arXiv preprint v2, 11 April 2026.
- URL: https://arxiv.org/abs/2604.02460
- Scope: three model families and matched reasoning-token budgets on multi-hop reasoning.
- Use: important negative result against inherent MAS efficiency.
- Limits: task scope is multi-hop reasoning; theoretical argument assumes idealized context use; paper identifies budget-control and benchmark artifacts.

## 3. Fu et al. — Do More Agents Help? Evaluating Accuracy and Cost in LLM Multi-Agent Workflows
- Status: arXiv preprint v2, 9 October 2026.
- URL: https://arxiv.org/abs/2606.05670
- Scope: BenchAgent; GPT-4.1; ten benchmarks; three runs; shared tool/evaluator/logging substrate and step limits.
- Use: pooled accuracy/cost comparisons, per-task gains and regressions, answer changes during synthesis.
- Limits: realized token use is not equalized; one fixed task sample per benchmark; one primary backend; GAIA/external runtime analyses are single-run or protocol-aligned rather than fully symmetric.

## 4. Ren et al. — OrchBench
- Status: arXiv preprint, 28 July 2026.
- URL: https://arxiv.org/abs/2607.25656
- Scope: deterministic DAG-based simulation of orchestration plans from 10 to 1,000 subtasks.
- Use: cheap screening of information transfer, parallelism, makespan and token efficiency.
- Limits: small model-level real-execution validation; Pearson r=0.816, p=0.047; Spearman rho=0.771, p=0.103; time/token correlations not significant; real resource use is framework-dependent.

## 5. Riedl — Emergent Coordination in Multi-Agent Language Models
- Status: peer-reviewed ICLR 2026; arXiv v4 dated 28 April 2026.
- URL: https://arxiv.org/abs/2510.05174
- Scope: information-theoretic emergence/PID framework; 600 experiments; four model families; ten-agent guessing game without direct agent messaging.
- Use: distinguish group-level alignment, redundancy, synergy and stable role differentiation.
- Limits: minimal coordination game; measured emergence does not by itself establish higher real-task utility; reported success rates similar across conditions.

## 6. Zhao et al. — SC-MAS: Constructing Cost-Efficient Multi-Agent Systems with Edge-Level Heterogeneous Collaboration
- Status: arXiv preprint, 14 January 2026.
- URL: https://arxiv.org/abs/2601.09434
- Scope: role selection, edge-specific collaboration strategies and LLM backbone assignment; MMLU, GSM8K, MATH, HumanEval, MBPP.
- Use: heterogeneous pairwise communication and model allocation as an architecture baseline.
- Limits: comparisons primarily against MAS construction baselines; DAG constraint excludes cycles/feedback; selection rationale has interpretability limits.

## 7. Wunderlich et al. — Multi-Agent Reasoning Improves Compute Efficiency: Pareto-Optimal Test-Time Scaling
- Status: ACL 2026 Student Research Workshop long paper.
- URL: https://arxiv.org/abs/2605.01566
- Scope: 34 configurations on MMLU-Pro and BBH; self-consistency, self-refinement, debate, mixture-of-agents.
- Use: bounded positive evidence for debate/MoA at equal modeled compute versus self-consistency.
- Limits: two benchmarks; limited base-model regimes; does not establish unique specialist-organ synergy.

## 8. Sanabria — OpenAI single-agent LLM architecture reduces computational overhead relative to multi-agent orchestration in a simulated mars rover decision-support benchmark
- Status: peer-reviewed original research, Frontiers in Robotics and AI, 6 July 2026.
- URL: https://doi.org/10.3389/frobt.2026.1877762
- Scope: 100 synthetic rover scenarios, GPT-4o/GPT-5.5, five repeats, prompt-defined specialists versus single agent.
- Use: compact fully contextualized task as a negative boundary condition; paired statistics and resource accounting.
- Limits: synthetic scenarios; two backends from one provider; prompt-defined agents rather than independent specialists; not operational rover ground truth.

## Evidence policy

The sources above do not demonstrate the full Cognitive Holobiont. They provide task-conditioned baselines, measurement methods, positive and negative boundary conditions. Do not merge their headline scores into one leaderboard because tasks, budgets, evaluation units and comparison baselines differ.
