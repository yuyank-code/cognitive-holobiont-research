# Claim–Evidence Matrix — Pass 37 Addendum
**Date:** 2026-11-22  
**Theme:** Causal collective value and matched-budget federation advantage.

| Claim / hypothesis | New evidence | Evidence status | Current interpretation |
|---|---|---|---|
| More agents generally improve performance | Kim et al. 180-configuration study; BenchAgent; equal-thinking-token study | Contradicted as a universal rule | Effects depend on task structure, baseline capability, topology and resource budget. |
| Parallelizable work can benefit from multi-agent coordination | Kim et al.; OrchBench; SC-MAS | Supported in bounded settings | Parallelism is a plausible source of net value when subtasks and information dependencies are real. |
| Sequential tasks benefit from agent decomposition | Kim et al.; Tran & Kiela; Frontiers rover study | Negative evidence in tested settings | Handoffs can fragment a shared reasoning trajectory and add coordination tax. |
| Heterogeneous specialists can be more efficient than homogeneous collaboration | SC-MAS | Preliminary / conditional | Edge-level interaction strategies and model allocation are promising; not yet proof against strongest single-agent baseline. |
| Multi-agent synergy can be measured | Riedl, ICLR 2026 | Supported in a minimal coordination game | PID-style measures distinguish group structure from independent behavior, but task utility must be measured separately. |
| Emergence implies higher task performance | Riedl, ICLR 2026 | Not supported | Measured coordination structure can change while group success remains similar. |
| A single model is always more efficient | Positive MoA/debate Pareto results; task-specific MAS wins | Contradicted as universal | Some multi-agent configurations improve accuracy at equal compute on selected benchmarks. |
| A strong single model may dominate when all context is available | Tran & Kiela; Frontiers rover study; BenchAgent | Supported in bounded settings | Compact, fully observed or sequential tasks are important single-agent regimes. |
| Task-conditioned orchestration can be screened cheaply | OrchBench | Preliminary | Simulation is useful for diagnosis, but current validation is small and resource predictions are framework-dependent. |
| Different role prompts constitute heterogeneous organs | Google scaling study; BenchAgent; SC-MAS distinctions | Not established | Prompt roles on shared backbones are not equivalent to independently trained specialists with durable expertise. |
| A federation creates unique capability beyond best-of-K | No decisive result in this pass | Open | Must use private-evidence partitions, ownership swaps, ablations and matched single-model information access. |
| A federation has a universal agent-count scaling law | Conflicting task-dependent results | Unsupported | Use task descriptors and measured budgets; do not hard-code a global threshold. |

## Key source distinctions

- **Peer-reviewed:** Riedl, ICLR 2026; Sanabria, Frontiers in Robotics and AI, 6 July 2026; Wunderlich et al., ACL 2026 Student Research Workshop.
- **Preprints:** Kim et al. (arXiv:2512.08296); Tran & Kiela (arXiv:2604.02460); Fu et al., BenchAgent v2 (arXiv:2606.05670); Ren et al., OrchBench (arXiv:2607.25656); Zhao et al., SC-MAS (arXiv:2601.09434).
- Do not treat vendor engineering descriptions, model leaderboards or unreviewed abstracts as independent scientific replication.

## Confidence updates

1. **High confidence:** agent count alone is not a valid proxy for collective value.
2. **High confidence:** task decomposition, dependency structure, context availability and coordination overhead materially affect outcomes.
3. **Medium confidence:** adaptive topology and edge-specific collaboration can improve the accuracy–cost frontier in selected settings.
4. **Medium confidence:** PID-style information decomposition can quantify some forms of group-level synergy, but its connection to external task utility remains task-dependent.
5. **Low confidence / unresolved:** a federation of independently trained heterogeneous organs has a persistent advantage over the strongest single-model, MoE, ensemble and workflow baselines under fully matched resources.
