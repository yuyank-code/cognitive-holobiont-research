# Contradictions and Open Problems — Pass 36 (2026-11-21)

## New contradictions

1. **Initial topology selection vs runtime mutation.** A strong task-conditioned initial graph may capture most available gains. Runtime edits must prove incremental causal value beyond a good router.
2. **Accuracy improvement vs resource efficiency.** MANTA's topology mutation improves its four-benchmark ablation but increases reported token use versus the no-mutation ablation. Reconfiguration is not automatically cheaper.
3. **Role novelty vs capability novelty.** MetaGen's role generation changes text-level specifications around a common backbone. It does not establish independent model expertise or a new organ.
4. **Task completion vs safety.** SEABench finds self-evolution can improve completion while causing later safety failures absent in paired frozen agents.
5. **Self-generated curriculum vs collapse.** MAE improves in tested settings but reports entropy decay and proposer collapse toward repetitive questions during prolonged training.
6. **Self-evaluation vs evaluator gaming.** MAE's Judge shares a backbone with Proposer and Solver; MetaGen's Architect relies on the base model's reasoning; research-agent reward hacking shows that even review panels can miss exploits.
7. **Dynamic flexibility vs static auditability.** Generated roles and graph edits increase adaptability but expand the configuration and security surface that must be reviewed.
8. **Fast adaptation vs long-term transfer.** A role or topology useful for one task can become harmful when persisted into a different task or permission context.
9. **Graph repair vs answer correctness.** A trace auditor can identify missing validators, duplicate writes or weak evidence paths without knowing whether the final answer is true.
10. **Evolution vs regeneration.** Rewiring an existing organ network or rewriting a role prompt is not equivalent to creating a specialist with a new validated capability.

## Open questions

1. Does runtime topology mutation add value after controlling for task-conditioned initial planning?
2. Which signals reliably indicate that the current organization is insufficient: low confidence, unresolved dependencies, failed tool calls, contradiction, missing verification, or execution anomalies?
3. Can a process auditor detect structural faults without overfitting to surface traces or confusing unusual-but-correct reasoning with failure?
4. How can the system distinguish a missing role from a missing capability that no existing model possesses?
5. Do generated roles remain behaviorally distinct after repeated cross-task reuse?
6. Does topology evolution transfer from homogeneous role-prompted agents to heterogeneous specialist models?
7. How much of reported benefit comes from an extra planning/evaluation pass rather than the structural mutation itself?
8. Can a mutation be evaluated on hidden held-out tasks without leaking the evaluator or its criteria to the proposer?
9. What independent authority approves changes to the Meta-Organ's own evaluator, permissions or safety rules?
10. Can rollback restore memory, permissions, tools, caches, and external side effects—not only the graph specification?
11. How should a system respond when a mutation improves average utility but causes a rare high-impact safety regression?
12. How can the Meta-Organ preserve specialist diversity instead of optimizing all roles toward the same reward and behavioral mode?
13. What is the correct unit of evolution: a role prompt, agent instance, model adapter, tool, bridge, graph edge, memory policy, or whole organ?
14. How should cumulative risk be measured when individually safe changes interact over many generations?
15. Can a persistent Meta-Organ detect and reverse a locally useful but globally harmful update without access to the original ground truth?
16. Does structural evolution produce any Holobiont-specific advantage beyond adaptive workflow search and learned routing?

## Unresolved threat classes

- evaluator tampering or reward hacking;
- role/skill persistence across context boundaries;
- privilege escalation through generated roles;
- prompt injection into mutation proposals;
- compromised audit logs or version registries;
- coordinated changes that weaken independent verification;
- self-modification that disables rollback or kill switches;
- common-mode failure across proposer, judge and specialist backbones;
- topology changes that route sensitive information to unauthorized organs;
- repeated small mutations that cumulatively erode diversity or safety constraints.
