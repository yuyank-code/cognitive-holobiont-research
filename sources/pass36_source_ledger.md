# Source Ledger — Pass 36 (2026-11-21)

## Peer-reviewed conference proceedings

### 1. MetaGen: Self-Evolving Roles and Topologies for Multi-Agent LLM Reasoning
- Authors: Yimeng Wang et al.
- Venue: Findings of EMNLP 2026, pp. 42721–42734.
- Link: https://aclanthology.org/2026.findings-emnlp.2005/
- Evidence: Query-conditioned role generation, graph construction and inference-time role/topology refinement; common DeepSeek-V3 backbone in main comparisons; GLM-4-Flash generalization on two benchmarks.
- Limitations: Same backbone does not establish heterogeneous organs; self-reinforcing bias, probabilistic safety and tool/prompt-injection risks are explicitly acknowledged.

### 2. Multi-Agent Evolve: LLM Self-Improve through Co-evolution
- Authors: Yixing Chen et al.
- Venue: EMNLP 2026, pp. 39563–39593.
- Link: https://aclanthology.org/2026.emnlp-main.1734/
- Evidence: Proposer–Solver–Judge co-evolution with shared Qwen2.5-3B backbone; +4.86 percentage points in the main overall comparison with unlabeled seed questions.
- Limitations: Shared backbone rather than independent organs; Proposer entropy decay/collapse; quality-filter removal causes reward/data contamination; coding gains are not uniformly superior to SFT.

### 3. AgentConductor: Topology Evolution for Multi-Agent Competition-Level Code Generation
- Authors: Siyu Wang et al.
- Venue: ICML 2026, PMLR 306:128828–128848.
- Link: https://proceedings.mlr.press/v306/wang26fk.html
- Evidence: Feedback-driven task-adapted DAG construction for code; up to +14.6% pass@1, -13% topology density and -68% token cost.
- Limitations: Code-centric evaluation; does not by itself establish long-horizon safe evolution of a specialist population.

### 4. Adaptive Graph Pruning for Multi-Agent Communication
- Authors: Boyi Li et al.
- Venue: ECAI 2025 proceedings; first published online 25 August 2026.
- DOI: https://doi.org/10.3233/FAIA251326
- Evidence: Joint hard node pruning and soft edge pruning; six text benchmarks; 460 mined supervision graphs; reported 91.04% average and up to 90% lower prompt tokens.
- Limitations: Fixed GPT-4o-mini backend in main paper; transfer to other families/scales open; text-only; not unrestricted online population evolution.

## Preprints

### 5. MANTA: Multi-Agent Network Topology Adaptation for Self-Evolving Multi-Agent Systems
- Authors: Mao-xun Huang et al.
- Date/version: 30 July 2026, arXiv:2607.28527.
- Link: https://arxiv.org/abs/2607.28527
- Evidence: Bounded inference-time edits to roles, links, order, visibility and validation paths; Gemma 4 31B; five benchmarks; reported average 74.0 vs 68.2 baseline.
- Limitations: 30 questions per benchmark and three runs; one mutation in main setup; process auditor is not correctness oracle; no human-labelled process-defect ground truth; mutation increased token use in reported ablation.

### 6. SEABench: Benchmarking Endogenous Misalignment in Self-Evolving Agents
- Authors: Saswat Das et al.
- Date: 28 September 2026, arXiv:2609.35596.
- Link: https://arxiv.org/abs/2609.35596
- Evidence: 48 longitudinal sequences and 480 task instances; controller, memory and tool/skill evolution; paired non-evolving controls; reports downstream safety failures absent in frozen counterparts.
- Limitations: Personal-assistant sandbox and bounded task sequences; needs broader replication.

### 7. Safety in Self-Evolving LLM Agent Systems: Threats, Amplification, and Case Studies
- Authors: Ruixiao Lin et al.
- Date: 22 June 2026, arXiv:2606.23075.
- Link: https://arxiv.org/abs/2606.23075
- Evidence: Module-lifecycle attack-surface matrix; 17 of 25 cells reported as critical; persistent attacks in two framework case studies.
- Limitations: Security analysis and two case studies; headline attack persistence/blocking rates are not universal population estimates.

### 8. Reward Hacking Challenges Oversight of Autonomous Research Agents
- Authors: Yue Huang et al.
- Date: September 2026.
- Link: https://www.microsoft.com/en-us/research/publication/reward-hacking-challenges-oversight-of-autonomous-research-agents/
- Evidence: 17 models, 38 tasks; spontaneous reward-hacking rates differ sharply between open-ended research pipelines and task-specific kernels; reviewer misses and feedback-related evasion reported.
- Limitations: Autonomous research-agent setting; not a direct multi-organ topology benchmark.

## Survey

### 9. A Survey of Self-Evolving Agents: What, When, How, and Where to Evolve on the Path to Artificial Super Intelligence
- Authors: Huan-ang Gao et al.
- Venue: Transactions on Machine Learning Research, 2026.
- Link: https://mlanthology.org/tmlr/2026/gao2026tmlr-survey/
- Use: Organizes evolution by what changes, when it changes and how; highlights safety, scalability and co-evolution challenges.
- Limitation: A field survey, not direct experimental validation of the Holobiont.

## Source-handling note

Peer-reviewed status is recorded separately from preprint status. Reported benchmark percentages are not compared across papers as if they shared a test set, backbone, budget or scoring protocol. All numerical results above are source-reported, not independently reproduced in this research pass.
