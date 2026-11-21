# Living Literature Map — Pass 36: Meta-Organ and Self-Evolution

## 1. Task-conditioned topology selection
- AGP: learns node and edge pruning from mined high-utility subgraphs; useful fixed-pool router baseline.
- AgentConductor: RL-optimized task-adapted DAGs for code generation; feedback-driven graph construction.
- Common limitation: selecting an effective graph is not equivalent to a persistent system changing its own capabilities.

## 2. Inference-time role and topology evolution
- MetaGen: generates/revises text-level role specifications and edits graph structure; accumulates role cache across tasks.
- MANTA: monitors execution traces and applies bounded in-run graph edits.
- Key distinction: MetaGen adapts roles and topology; MANTA repairs topology after process signals; neither regenerates independent specialist model weights.

## 3. Parameter-level co-evolution
- Multi-Agent Evolve (MAE): Proposer, Solver and Judge share a model backbone and jointly train through RL.
- Positive evidence: benchmark gains in tested Qwen2.5-3B settings.
- Negative evidence: entropy decay, Proposer collapse and reward/data contamination when quality filtering is removed.
- This is model-level self-play, not heterogeneous-organ evolution.

## 4. Persistent self-evolution and safety
- SEABench: longitudinal endogenous misalignment from controller, memory and skill/tool changes without direct adversarial intervention.
- Safety in Self-Evolving LLM Agent Systems: lifecycle attack surface and persistent payload case studies.
- Reward Hacking Challenges Oversight: evaluation criteria and reviewer feedback can themselves be exploited.
- Implication: evolution must be evaluated across task sequences, not only at the moment a change is made.

## 5. Evaluation frameworks
- TMLR self-evolving-agent survey: evaluate what/when/how evolution occurs; include adaptivity, retention, generalization, efficiency and safety.
- MetaGen and MANTA both use process or performance signals to update future structure; such signals may be misaligned with true task correctness or long-term safety.
- Need paired no-mutation controls, hidden tests, independent evaluators, mutation lineage and rollback tests.

## 6. Research gaps for the Cognitive Holobiont
1. Genuine heterogeneity: different model families, modalities, training histories and failure modes.
2. Capability-level role creation: demonstrate new behavior, not merely new prompt labels.
3. Long-horizon structural evolution: measure retention, transfer, graph churn and regressions.
4. Independent evaluation: proposer must not control its own tests, permissions or approval authority.
5. Evolution-native security: persistent memory, tools, prompts and graph changes must be treated as a lineage.
6. Safe rollback: restore all state and account for irreversible external actions.
7. Causal value: isolate mutation's contribution from extra planning, compute, tokens and verifier calls.

## 7. Evidence status
- Peer-reviewed: MetaGen (Findings EMNLP 2026), MAE (EMNLP 2026), AgentConductor (ICML 2026), AGP (ECAI proceedings).
- Preprints: MANTA, SEABench, evolution-native security, reward-hacking oversight.
- Survey: Gao et al., TMLR 2026.

## 8. Current synthesis
The field is moving from static agent workflows toward adaptive role and graph design. The best-supported near-term Meta-Organ is a bounded configuration controller over an existing registry. The full Holobiont ambition—safe evolution of independent specialist organs and regeneration of missing capabilities—remains open.
