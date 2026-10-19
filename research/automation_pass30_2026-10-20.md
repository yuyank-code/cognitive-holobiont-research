# Cognitive Holobiont Research — Pass 30
Date: 2026-10-20

## Result
New trajectory-level and controlled-efficiency evidence suggests that collaboration must be evaluated for preserving strong initial proposals and adding verified value, not merely for producing polished consensus. The Treatise/PDF remains a hypothesis, not established fact. Implementation remains deferred.

## Evidence
**MASTraceBench** (preprint, arXiv:2609.34496; https://arxiv.org/abs/2609.34496) studies six cooperative/competitive tasks. The authors report final multi-agent answers rarely surpass the strongest initial proposal; weaker proposals often move toward strong ones, while strong proposals can regress. Claim-level CLEARS reportedly performs best on five of six tasks. Limitation: small task suite and strongest-initial score is an evaluator-side oracle unless a practical selector can identify it.

**Rethinking Efficiency Methods for MAS** (preprint, https://arxiv.org/abs/2609.05933) uses a shared backbone/registry/runtime and 38 diagnostic cells across four task families. It reports topology/pruning gains can be setup-dependent; random pruning sometimes preserves similar accuracy, and structural collapse or disabled tools can masquerade as efficiency. Every optimizer must beat same-budget random pruning, its unoptimized parent, and a strong single-agent baseline.

**Semantic Cooperative Games** (preprint, https://arxiv.org/abs/2607.18255) computes trace-based semantic attribution cheaply. In a three-agent HealthBench workflow constructed to satisfy its assumptions, SLIC reports Kendall tau 0.814 and L1 error 6.61 versus a Monte Carlo Shapley reference. However, support extraction and rubric/judge errors can distort attribution; trace attribution is not inherently causal.

**More Capable, Less Cooperative?** (peer-reviewed ICML 2026, https://proceedings.mlr.press/v306/yadav26a.html) finds capability does not predict cooperation in a constructed zero-cost sharing environment; explicit protocols help competence-limited agents. Transfer to privacy-constrained long-horizon tasks remains open.

**AgentWorld** (preprint, https://arxiv.org/abs/2609.31590) tests 25–55 rounds with asymmetric roles. Its best primary model achieves 52% task success; its CCE metric uses an LLM-built causal action graph, which still needs auditing.

## Revised hypothesis
Use independent proposals; elicit missing facts; exchange claims/evidence selectively; preserve provenance; treat semantic traces as diagnostics; test learned topology against matched random pruning; validate attribution with interventions; verify final outcomes and risk-specific constraints; count all compute, context, tool, verification, latency, and privacy costs.

## Math and falsification
Let U(p) be independently verified utility. The evaluator-side ceiling is U_oracle=max_i U(p_i), but this is not a deployable baseline. Compare collaboration against a practical best-of-K selector with the same verifier budget:
Delta_net = U(p_collab) - U(selector_B(p_1,...,p_K)).
For learned topology T and random-pruned control R at matched structural budget:
Delta_structure = U(T)-U(R).
Report paired uncertainty across tasks/seeds. Distinguish fixed-continuation interventions from rerun-with-replanning interventions; they estimate different contributions.

Falsify or weaken Holobiont-specific synergy if gains vanish against matched best-of-K selection, random pruning, ownership swaps, or held-out tasks, or if trace attribution fails intervention audits. No universal topology, latent protocol, or fixed agent count is supported.
