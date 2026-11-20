# Source Ledger — Pass 35 (2026-11-20)

## From Private Experience to Collective State: A Survey of Multi-Agent Memory Formation and Maintenance
- Authors: Yiqi Wang, Jiaqi Zhang, Zhangkai Wu, Mingkai Zheng, Zequn Sun, Yiqun Duan, Zirui Liu, Zhihao Hao, Taotao Cai.
- Status: preprint; posted to SSRN 15 September 2026; 62-page survey. Not treated as peer-reviewed in this pass.
- DOI/archive: https://doi.org/10.5281/zenodo.22288996
- Repository: https://github.com/xiaoqi-7/Multi-Agent-Memory-Survey
- Use: OTGE framework; 89-paper coded corpus; lifecycle operator coverage; six guarantees; evaluation gaps.
- Key figures: admission 77/89; revision 52/89; propagation 36/89; scoping 25/89; reconciliation 22/89; revocation 12/89; recovery 6/89.
- Critical boundary: curated literature survey and coding instrument, not a causal experiment. Counts depend on inclusion criteria and operator coding.

## AMA-Bench: Evaluating Long-Horizon Memory for Agentic Applications
- Authors: Yujie Zhao et al.
- Status: peer-reviewed, ICML 2026, Proceedings of Machine Learning Research 306:162781–162809.
- Official paper: https://proceedings.mlr.press/v306/zhao26bs.html
- Use: real agent-environment trajectories; causal/objective state memory; AMA-Agent.
- Key result: AMA-Agent reports 57.22% accuracy, 11.16 percentage points above the strongest baseline on AMA-Bench.
- Critical boundary: benchmark and memory architecture; not a heterogeneous multi-agent memory-governance experiment.

## Learning to Remember: End-to-End Training of Memory Agents for Long-Context Reasoning
- Authors: Kehao Zhang, Shangtong Gui, Sheng Yang, Chen Wei, Yang Feng.
- Status: peer-reviewed, EMNLP 2026, pages 29575–29599.
- Official paper: https://aclanthology.org/2026.emnlp-main.1299/
- Use: Unified Memory Agent (UMA), query-agnostic proactive memory maintenance, structured CRUD bank, Ledger-QA.
- Key result: at 16k budget, UMA-Generalist has the highest aggregate score among compared methods on the paper's test-time-learning and accurate-retrieval benchmarks; UMA-Specialist improves Ledger-QA after task adaptation.
- Critical boundary: single-agent setting, fixed tool interface, synthetic Ledger-QA diagnostic; collaborative agents and evolving APIs left for future work.

## TRACE: Governing Memory Validity in Evolving Multi-Agent Systems
- Authors: Wenjun Xiong et al.
- Status: arXiv preprint submitted 27 September 2026.
- Paper: https://arxiv.org/abs/2609.33517
- Code: https://github.com/xiong-wenjun/TRACE
- Use: temporal memory admission at agent return; explicit/implicit invalidation; obligation-aware Return View.
- Key result: 92.6–98.3% valid-information availability and 98.4–99.5% invalid-information rejection on derived ManBench-Return; STALE Type II gains are reported with substantial token cost.
- Critical boundary: assumes authenticated return, checkpoint and source receipts; verifier/candidate coverage matter; longer absences degrade performance; not a general memory-poisoning defense.

## MemTX: Transactional Belief Commit for Stateful Agent Memory
- Authors: Xiaoyang Li, Yiqi Wang, Haohui Lu, Zhi Chen, Mo Li, Pingan Song, Taotao Cai.
- Status: arXiv preprint, under review, submitted 27 July 2026.
- Paper: https://arxiv.org/abs/2607.23929
- Code: https://github.com/lxy1134/MEMTX
- Use: staged writes, belief commit, snapshot isolation, action gating, typed cascade repair.
- Scope: 90-case main suite, 56-case hardened suite, five backbones; bounded enumeration of 5,530,160 protocol states and 10,537,260 transitions.
- Critical boundary: LLM path exercises weaker gate; provenance gaps and transaction-retry escapes remain; repair only follows recorded lineage; no environment-level replay.

## MAPLE-Guard: Memory-Aware Link Enforcement Against Memory-Link Poisoning in Multi-Agent Systems
- Authors: Wenjun Xiong et al.
- Status: arXiv preprint; v1 1 August 2026, v2 3 October 2026.
- Paper: https://arxiv.org/abs/2608.00426
- Code: https://github.com/xiong-wenjun/MAPLE-Guard
- Use: lifecycle gates at write, retrieval, promotion and cross-agent reuse.
- Key result: AppWorld action-selection proxy with Gemma Base: full lifecycle guard 88.4% MDSR@3 and 0.1% RDA@3 vs retrieval-only 65.0% and 21.6%.
- Critical boundary: attacker cannot modify hidden metadata/topology; assumes reliable provenance and retrieval traces; full-feedback setting uses evaluator outcomes; heuristic risk rules; not uniformly cost-free.

## MemoryDojo: Benchmarking Poisoning Through LLM Agent Memory
- Authors: David H. Yang, Blake Bullwinkel, Amanda J. Minnich, Mohammad Mohammadi Amiri, Giorgio Severi.
- Status: arXiv preprint submitted 6 November 2026.
- Paper: https://arxiv.org/abs/2611.09721
- Official research page: https://www.microsoft.com/en-us/research/publication/memorydojo-benchmarking-poisoning-through-llm-agent-memory/
- Use: 155 multi-session trajectories, four domains, five memory systems; insertion, persistence, propagation, retrieval and behavioral reach.
- Key result: all five evaluated memory systems are susceptible; memory-aware poison optimization raises attack success by approximately 2–31% in evaluated settings.
- Critical boundary: sandboxed task suites, synthetic trajectories and local memory; data/code/integrations are stated as forthcoming in the paper.

## When Agents “Misremember” Collectively: Exploring the Mandela Effect in LLM-Based Multi-Agent Systems
- Authors: Naen Xu et al.
- Status: peer-reviewed, ICLR 2026.
- Paper: https://arxiv.org/abs/2602.00428
- Conference poster: https://iclr.cc/media/iclr-2026/Slides/10006567_wqA8k4m.pdf
- Code/data: https://github.com/bluedream02/Mandela-Effect
- Use: MANBENCH, 20 tasks, 4,838 questions, five protocols, 13 LLMs; collective false memory and source-scrutiny defenses.
- Key result: average 74.40% reduction in measured Mandela effect with evaluated defenses.
- Critical boundary: multiple-choice controlled benchmark; open-ended team interactions and dynamic roles need further study.

## Memory Provenance Laundering in LLM Agents: A Non-Amplification Firewall for Persistent Memory
- Authors: Jinghan Xu, Yiyong Xiao, Wanru Shao, Hankai Liu, Xinjin Li.
- Status: arXiv preprint submitted 31 July 2026.
- Paper: https://arxiv.org/abs/2607.29167
- Use: provenance-preserving memory firewall (PPMF), source-authority non-amplification and action-risk gating.
- Key result: in the schema-grounded evaluation, no evaluated unauthorized high-risk action passes when platform-maintained provenance, confirmation and risk labels remain intact.
- Critical boundary: preprint and strong metadata assumptions; result is not a universal guarantee.

## Position: Multi-Agent Systems Should Prioritize Concurrency Control
- Authors: Xin Yang, Letian Li, Zimo Ji, Terry Jingchen Zhang, Wenyuan Jiang.
- Status: peer-reviewed position paper, ICML 2026, PMLR 306:172725–172740.
- Official paper: https://proceedings.mlr.press/v306/yang26dy.html
- Use: maps shared-state failures to stale reads, lost updates and inconsistent outcomes; recommends explicit conflict detection and isolation.
- Critical boundary: position paper, not an empirical comparison of specific isolation protocols.
