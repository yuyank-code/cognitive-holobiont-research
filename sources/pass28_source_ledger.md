# Source Ledger — Pass 28 (2026-10-18)

## The Ringelmann Effect in Multi-Agent LLM Systems: A Scaling Law for Effective Team Size
- Authors: Blaž Bertalanič and Carolina Fortuna.
- Status: arXiv preprint posted 2026-05-31; not treated as peer-reviewed here.
- Links: https://arxiv.org/abs/2606.02646 ; https://arxiv.org/html/2606.02646
- Use: dependence-adjusted effective-team-size model; conformity and answer diversity.
- Scope: 44 model/task/condition cells; core MMLU-Hard, GSM-Hard, GPQA tasks; team sizes up to 30; core sweep is homogeneous, role-symmetric, fully connected debate with selected heterogeneity/sparse conditions.
- Limits: not long-horizon, tool-using, asymmetric-specialist, or multimodal MAS; answer entropy can count distinct wrong answers; exchangeability-style assumptions; no multiple-comparison correction for reported pre-registered contrasts; held-out team-size prediction does not certify cross-domain generality.

## Revisiting Multi-Agent Debate as Test-Time Scaling: A Systematic Study of Conditional Effectiveness
- Link: https://arxiv.org/abs/2505.22960
- Status: public preprint.
- Use: matched-generation comparisons with self-refinement and self-consistency; debate is not a consistent winner, though gains appear on some harder math tasks.
- Limits: selected mathematical and safety tasks; model/task/aggregation-specific.

## Talk Isn't Always Cheap: Understanding Failure Modes in Multi-Agent Debate
- Link: https://arxiv.org/abs/2509.05396
- Status: public preprint.
- Use: reports both improvements and regressions across CommonSenseQA, MMLU, and GSM8K.
- Limits: selected models, datasets, prompts, and two debate rounds.

## Towards a Science of Scaling Agent Systems
- Link: https://arxiv.org/abs/2512.08296
- Status: public preprint; check the current version before reusing statistics from earlier versions.
- Use: task-conditional agent scaling; aggregate averages can hide positive and negative task-specific effects.
- Limits: finite task/configuration coverage; predictive fit is not a universal causal law.

## Persistent Memory in Multi-Agent LLM Inference: What It Costs, What It Buys, and When You Can Tell
- Authors: Hochan Son, Kyungdoe Han, Jaehan Koh, Xiaowu Dai, Wenlu Xu, Guang Cheng.
- Status/date: arXiv preprint posted 2026-10-06.
- Links: https://arxiv.org/abs/2610.07782 ; https://arxiv.org/html/2610.07782
- Use: controlled memory ablation and measurement audit; separates agent decomposition/peak KV from persistent trace recall.
- Reported result: across eight dataset pairs at n=100 per arm, recall accuracy difference +0.015, 95% CI [-0.011, +0.046]; peak KV cost +0.368 MiB, 95% CI [+0.167, +0.590].
- Limits: one system/team; some comparisons only two to four replicates; independent-item benchmark makes cross-session memory difficult to test; authors say broader efficacy is untested, not disproven.
- Transferable methods: assert component execution; test read/write reachability; avoid self-retrieval contamination; vary one factor; counterbalance order; report reproducibility bands.

## ProtocolBench: Which LLM MultiAgent Protocol to Choose?
- Link: https://arxiv.org/abs/2510.17149
- Author-hosted publication record: https://www.hongyidu.ai/papers/protocolbench
- Code/data: https://github.com/ulab-uiuc/AgentProtocols
- Status: author record identifies ICML 2026.
- Use: protocol comparisons across success, latency, message/byte overhead, and failure robustness; reports scenario-specific ProtocolRouter gains.
- Reported on author page: up to 36.5% completion-time variation across protocols; 3.48 s mean latency difference; up to 18.1% lower Fail-Storm recovery time versus best fixed-protocol baseline.
- Limits: scenario-specific; include router overhead and validate held-out tasks before generalizing.

## Evidence discipline
These sources are not direct replications; they differ in tasks, models, budgets, metrics, and interaction structures. Distinguish peer-reviewed work from preprints, reported findings from interpretation, and null findings from universal claims.
