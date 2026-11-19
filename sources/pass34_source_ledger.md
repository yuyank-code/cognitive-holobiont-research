# Source Ledger — Pass 34 (2026-11-19)

## When Messages Go Wrong: Understanding Communication Faults in LLM-Based Multi-Agent Systems
- Authors: Jinhao Zhou, Xiaoyu Zhang, Jiongchi Yu, Fahao Chen, Jun Wu.
- Status/date: arXiv preprint submitted 11 October 2026; not peer-reviewed in this pass.
- Link: https://arxiv.org/abs/2610.15459
- Use: semantic and partial-content communication faults, silent failure, topology-dependent evidence-path resilience.
- Scope: >29,000 executions, 100 tasks, five domains, three workflow topologies, three model configurations.
- Key findings: 20.7% silent failures among failures with complete detection records; 76.2% for partial-content faults; Flat 53.0% task success versus Sequential 3.3% and Hierarchical 3.2% under the study's injected communication faults.
- Critical boundary: Flat's alternate branch already has worker evidence and mainly protects the downstream evidence handoff; upstream/shared-source faults defeat it. Fresh evidence reacquisition helps only while an unaffected source/path remains.

## AgentChaos: Chaos Engineering for Agent Systems via Programmatic Fault Injection
- Authors: Gou Tan, Zhensu Sun, Jieke Shi, Ting Zhang, Zilong He, Qingfu Wu, Shuai Liang, Weifeng Sun, Junda He, Pengfei Chen, Chuanfu Zhang, Lwin Khin Shar, David Lo.
- Status: peer-reviewed, Proceedings of ASE 2026, 12–16 October 2026.
- DOI: https://doi.org/10.1145/3832783.3837437
- arXiv: https://arxiv.org/abs/2608.06790
- Use: runtime HTTP-layer fault injection for LLM API responses; crash, omission and value faults in content and tool-call fields.
- Scope: 65 fault configurations, five architectural patterns, seven benchmarks, four task domains, four backbone models.
- Key findings: pass@1 can drop by up to 50 percentage points; truncation diagnosis 4.3% in the reported rule-based analysis; robustness rankings similar across tested backbones.
- Critical boundary: one system per architecture pattern; unified Google ADK reimplementation; sparse triggered cases per fault configuration; pass@1 does not capture all partial correctness.

## RCR-Router: Role-Conditioned Context Routing for Resource-Efficient Multi-Agent LLM Systems
- Authors: Jun Liu et al.
- Status: peer-reviewed, Findings of EMNLP 2026, pages 8938–8963.
- DOI: https://doi.org/10.18653/2026.findings-emnlp.425
- Official page: https://aclanthology.org/2026.findings-emnlp.425/
- Use: role-, task-stage- and token-budget-conditioned selection of structured shared-memory items.
- Key findings: 35% average token reduction and 38% average runtime reduction relative to Full-Context while maintaining or improving performance.
- Scope: multi-hop QA, ALFWorld and WebShop.
- Critical boundary: does not demonstrate long-horizon narrative continuity, adversarial provenance, or latent-state communication.

## Routed Graph Handoff: Adaptive Format Selection for Multi-Agent LLM Delegation
- Authors: Pratyay Banerjee and Ankit Chadha.
- Status: peer-reviewed, Findings of EMNLP 2026, pages 42756–42765.
- DOI: https://doi.org/10.18653/2026.findings-emnlp.2008
- Official page: https://aclanthology.org/2026.findings-emnlp.2008/
- Use: router-selected typed dependency graph versus natural-language handoff.
- Key findings: natural-language messages consume 40–60% of token budget in studied systems; hybrid routing matches/exceeds NL-only across four benchmarks and 1,050+ trajectories; graph-only regresses 14.6 pp on AppWorld without the router.
- Critical boundary: does not test latent bridges or long-term memory.

## RouterHGC: Optimized Router for LLM-based Multi-Agent Systems via Heterogeneous Graph Contrastive Learning
- Authors: Yitao Xiao, Shaoyong Guo, Guoming Yang, Qingnan Wang, Yinlin Ren, Xuesong Qiu, Qi Feng.
- Status: peer-reviewed, Findings of ACL 2026, pages 31759–31789.
- DOI: https://doi.org/10.18653/v1/2026.findings-acl.1589
- Official page: https://aclanthology.org/2026.findings-acl.1589/
- Use: query-conditioned selection of agent roles, models and collaboration modes.
- Key findings: 0.80%–6.17% accuracy gains on MATH/HotpotQA and 27.40% lower inference cost in the reported experiments.
- Critical boundary: five public datasets; no fault-injection or long-horizon persistent memory evaluation.

## Repair or Resample? Rethinking Failure Debugging in LLM Multi-Agent Systems
- Authors: Zhongwen Luan, Xiaoyu Zhang, Ming Hu, Yue Yang, Jiongchi Yu, Xiaohong Chen.
- Status: arXiv preprint submitted 26 August 2026, revised 29 August 2026.
- Link: https://arxiv.org/abs/2608.25920
- Use: SymTrace replay anchors and SymFail failure trajectories; distinguishes stochastic reruns from causal repair.
- Scope: 536 human-annotated failure trajectories, three MAS frameworks.
- Key findings: unguided reruns reproduce failures 67.97% of the time and repair 6.90%; symptom-driven intervention repairs 20.15%.
- Critical boundary: preprint and bounded trajectory-debugging setting; not neural organ regeneration.
