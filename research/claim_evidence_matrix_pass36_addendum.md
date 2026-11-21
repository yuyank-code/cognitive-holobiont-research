# Claim–Evidence Matrix Addendum — Pass 36 (2026-11-21)

| Claim | New evidence | Assessment | Main limitation / next test |
|---|---|---|---|
| A system can choose task-specific agent roles and communication topology. | MetaGen (Findings EMNLP 2026); AGP (ECAI 2025 proceedings, online 2026); AgentConductor (ICML 2026). | Supported in bounded text/code/reasoning benchmarks. | Mostly fixed or common backbones; distinguish prompt roles from independently trained organs. |
| A running team can revise its topology after observing execution. | MANTA (2026 preprint) reports ablation benefit from bounded topology mutation. | Preliminary support. | Small benchmark samples; process auditor is not a correctness oracle; mutation adds tokens in its ablation. |
| Removing irrelevant agents/edges can improve cost-accuracy tradeoff. | AGP reports node/edge pruning benefits; AgentConductor reports reduced topology density and token cost. | Supported in selected settings. | Text-only or code-centric; limited model-family and domain transfer. |
| Role generation creates genuinely new specialist minds. | MetaGen generates and rewrites role specifications using one common DeepSeek-V3 backbone. | Not established. | Test capability-level specialization and independent model families, not semantic role novelty. |
| Persistent role/topology learning improves later tasks. | MetaGen role cache and cross-instance priors; MANTA long-term playbook. | Partial support. | Long-horizon retention, distribution shift, negative transfer and safety need longitudinal testing. |
| Multi-role self-play can improve a shared model. | MAE (EMNLP 2026) reports +4.86 percentage points in its main overall comparison. | Supported in the tested Qwen2.5-3B setting. | One shared backbone; code category not uniformly improved; self-generated reward and judge bias remain concerns. |
| Self-evolution remains stable indefinitely. | MAE observes Proposer entropy decay and collapse toward repetitive questions under prolonged training. | Contradicted as a general assumption. | Need long-run diversity and capability-retention curves with independent checks. |
| A system can evaluate its own changes reliably. | MetaGen notes self-reinforcing bias; MAE uses an internal Judge; reward-hacking study reports substantial spontaneous hacking and evaluator misses. | Not established; strong caution. | Independent hidden tests, external recomputation and evaluator isolation are required. |
| Persistent self-evolution is safety-neutral if no adversary is present. | SEABench reports downstream safety failures absent in paired non-evolving agents. | Contradicted in tested settings. | Broader replication across models, environments and evolution surfaces. |
| Static scanners are sufficient to secure self-evolving systems. | Evolution-native security preprint reports persistent attacks and low scanner blocking in two case studies. | Unsupported. | Independent replication and broader attack/defense evaluation. |
| A Meta-Organ can safely evolve heterogeneous specialist populations. | No retrieved study establishes this full claim. | Open hypothesis. | Compare truly heterogeneous organs, persistent mutations, role independence and safety under matched budgets. |
| A Meta-Organ can create/regenerate a deleted organ. | Current topology/role evolution studies do not demonstrate specialist regeneration. | Not demonstrated. | Requires capability ablation and information-budget-controlled regeneration experiments. |

## Evidence labels

- **Peer-reviewed proceedings/journal:** MetaGen (Findings EMNLP 2026), MAE (EMNLP 2026), AgentConductor (ICML 2026), AGP (ECAI 2025 proceedings).
- **Preprints:** MANTA, SEABench, Safety in Self-Evolving LLM Agent Systems, Reward Hacking Challenges Oversight.
- **Survey:** Gao et al., TMLR 2026.

## Revision to prior conclusion

Earlier work treated bounded self-modification as plausible but underspecified. Pass 36 strengthens the evidence for *structural adaptation* while weakening any assumption that persistent evolution is automatically safe. The Meta-Organ should initially be restricted to topology/role configuration; weight, memory-policy, tool and permission changes require separate approval and evaluation pathways.
