# Contradictions and Open Problems — Pass 30 (2026-10-20)

## C-066: Interaction can damage strong proposals
MASTraceBench reports that final MAS answers rarely exceed the strongest initial proposal across six tasks; weak proposals often improve while strong ones may regress. Preprint and task-suite limitations apply. Test trajectories and compare with a matched best-of-K selector.

## C-067: Learned topology may not beat random pruning
A controlled efficiency preprint reports that random pruning sometimes preserves accuracy and that some reported gains arise from setup artifacts or disabled tools. Require identical starting graphs, tools, role registry, structural budget, and multiple random seeds.

## C-068: Semantic trace attribution is not causal ground truth
Semantic Cooperative Games derives contribution from recovered support logic in a realized trace. Negation, paraphrase, parallel support, masking, and rubric errors can distort it. Validate against interventions.

## C-069: Capability is not cooperation
Peer-reviewed ICML 2026 evidence finds capability and sharing can diverge in a constructed environment. Test knowledge, teammate-awareness, disclosure, integration, and authorization failures separately.

## Open questions
1. Does claim-level exchange preserve decisive minority evidence better than whole-proposal debate?
2. Can a practical selector beat collaboration using the same initial proposals and verifier budget?
3. Do learned topology methods beat matched random pruning on held-out tasks?
4. Does trace attribution predict fixed-continuation and rerun-with-replanning effects separately?
5. Can these gains survive ownership swaps, long-horizon state changes, privacy limits, and risk-specific checks?

## Falsification conditions
Weaken Holobiont-specific synergy if collaboration fails against matched best-of-K selection; topology gains vanish against random pruning; trace attribution fails intervention audits; or gains disappear under ownership swaps and held-out task families. Do not generalize a failed configuration to all MAS.
