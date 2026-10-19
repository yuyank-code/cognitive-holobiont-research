# Pass 30 Claim–Evidence Addendum (2026-10-20)

- **Proposal preservation:** MASTraceBench (preprint, arXiv:2609.34496) reports that final MAS answers rarely surpass the strongest initial proposal across six tasks; claim-level CLEARS reportedly leads on five. Status: collaboration is not a monotonic refinement process. Test against a practical best-of-K selector; evaluator-side best-initial is only a diagnostic ceiling.
- **Topology efficiency:** the controlled preprint arXiv:2609.05933 reports setup-dependent pruning gains and cases where random pruning preserves accuracy. Status: learned topology must beat same-budget random pruning, the parent graph, and single-agent controls.
- **Contribution attribution:** Semantic Cooperative Games (arXiv:2607.18255) offers cheaper trace-derived semantic attribution, but support extraction/rubric errors remain. Status: diagnostic only until validated against interventions.
- **Capability/cooperation:** peer-reviewed ICML 2026 study reports capability does not predict cooperation in a constructed zero-cost sharing environment. Status: do not assume stronger models will share/integrate better.
- **Long horizon:** AgentWorld (arXiv:2609.31590) reports 52% best primary task success; its CCE uses an LLM-built action graph. Status: task-state verification helps, but causal-graph validity needs auditing.

Keep separate: proposal quality, selector quality, oracle ceiling, semantic attribution, intervention effect, task utility, risk violations, and full costs.
