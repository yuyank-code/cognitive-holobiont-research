# Automation Research Pass 09 — 2026-09-10

## Scope
Fresh pass over latent communication, modularity/MoE, model stitching, uncertainty, topology/security, consensus/ensembles, hypernetworks, and recursive self-improvement. The treatise remains a hypothesis/specification, not established fact.

## Meaningful new findings

1. **Topology is now both a performance variable and a security/control variable.** TopoDIM reports 46.41% lower token consumption with a 1.50% average performance improvement over tested baselines; Graph-GRPO frames topology learning as a credit-assignment problem and optimizes edges by relative performance; TopoSHIELD dynamically prunes risky edges and reports lower attack spread while preserving utility. This triangulates a stronger conclusion: the Holobiont communication graph should be adaptive, but topology optimization must jointly account for utility, coupling, uncertainty, and attack conductivity rather than optimize task score alone.

2. **Communication can expose the architecture itself.** CIA shows that MAS communication topology can be inferred in a black-box setting. CORBA shows that the collaboration process can be attacked through contagious recursive blocking. Lying with Truths shows that individually truthful evidence fragments can be coordinated to induce a false collective belief. Therefore provenance/security must include not only node authenticity but graph privacy, dependency structure, and composition-level manipulation.

3. **Uncertainty is becoming trajectory/topology-aware.** MATU models full reasoning trajectories, communication paths, and topology rather than only final answers. This supports replacing independent per-specialist confidence with a dependency-aware reliability model. The Holobiont should discount evidence whose causal ancestry overlaps heavily with other evidence.

4. **Consensus is no longer a necessary aggregation primitive.** Free-MAD removes forced consensus and evaluates whole debate trajectories; the 2025 Voting-or-Consensus study found more discussion rounds can reduce performance; the 2026 confidence/diversity study reports gains from diversity-aware initialization and calibrated confidence. The current hypothesis is therefore evidence-weighted commitment with explicit dissent/abstention, not majority agreement.

5. **There is positive evidence that structured multi-agent fusion can beat a single agent, but this is not yet evidence for the Holobiont.** ConSensus reports 7.1% average accuracy improvement over a single-agent baseline on multimodal sensing and 12.7x lower fusion-token cost than iterative debate. This is useful positive evidence for heterogeneous complementary specialists, but it remains task- and benchmark-specific and does not establish causal distributed computation or resilience advantages.

6. **Model stitching provides a stronger interoperability baseline.** Revisiting Model Stitching in the Foundation Model Era finds heterogeneous vision foundation models can be stitched reliably when the stitch objective and location are appropriate, while shallow/naive stitching can fail. StateBridge adds training-free hidden-state alignment evidence. Thus a Holobiont should not claim novelty merely from connecting heterogeneous specialists; novelty requires selective interfaces plus resilience/recovery properties beyond stitching.

7. **Hypernetwork evidence continues to support adaptation generation, not information-free regeneration.** Scaling Laws for Hypernetwork-Based Knowledge Injection reports predictable scaling and OOD generalization for hypernetwork-generated LoRA adapters. SHINE similarly maps context to LoRA in one pass. The theoretical limit remains: if unique capability information is absent from every surviving state, no hypernetwork can recover it without external information. Regeneration experiments therefore need behavioral equivalence, OOD transfer, calibration, and conflict/collateral-regression tests, not parameter similarity.

8. **MoE theory is improving but does not establish durable cognitive organs.** ZipMoE gives theory and empirical gains for parameter-efficient expert building blocks; Guided by the Experts provides feature-learning dynamics for soft-routed MoE; CoPRIME explicitly regularizes specialization and diverse utilization. These establish increasingly principled ways to induce specialization, but the Holobiont claim remains stronger: an organ must retain causally identifiable function under continued training, perturbation, routing changes, and communication.

9. **Recursive self-improvement remains most credible when governance is separated from the mutable substrate.** Recent governed recursive-improvement architecture work explicitly separates goals/scope/tools/benchmarks, an external governance plane, memory, routing, and an improvement policy. This is consistent with the emerging Holobiont architecture of a relatively stable meta-process supervising reversible changes to memory, adapters, routing, and topology. It is not evidence for unrestricted recursive rewriting of the core learner.

## Claim-evidence revisions

- **CH-003 latent novel-information transfer:** Partially supported, conditional. Causal sender-specific transfer has positive evidence, but aggregate latent-relay gains remain confounded in some regimes.
- **CH-005 shared latent space required:** Weakly supported -> unsupported. Model stitching and StateBridge favor explicit learned or closed-form interface maps instead of one global latent geometry.
- **CH-007 communication improves collective intelligence:** Narrowed. Supported only under task/complementarity/topology conditions; SILO-BENCH remains strong negative evidence for naive scaling.
- **CH-009 consensus improves truth:** Unsupported as a general principle. Replace with calibrated, provenance/dependency-aware evidence aggregation with dissent preservation.
- **CH-011 distributed redundancy gives resilience:** Strongly supported in principle, but correlated failure and evidence dependence remain the key unresolved limit.
- **CH-013 hypernetwork regeneration:** Partially supported for adaptation/parameter generation; unsupported for recovery of genuinely unique destroyed information.
- **CH-015 adaptive topology:** Partially supported for efficiency and robustness; still unproven as a mechanism for preserving functional diversity under adversarial/common-mode conditions.
- **CH-017 recursive self-rearchitecture:** Plausible only in bounded, validation-gated substrate/harness changes; unrestricted core self-rewrite remains speculative.

## Contradiction log additions

- More communication can improve complementary sensing yet harm distributed algorithmic coordination; communication value is topology- and task-dependent.
- Consensus-oriented debate can improve some benchmarks, while longer debate rounds can degrade performance and consensus-free methods can outperform it.
- Heterogeneous model stitching can work well with appropriate interface training, while naive shallow stitching fails; interoperability is therefore conditional rather than intrinsic.
- Hypernetworks can scale knowledge injection, but this does not imply recoverability after unique information destruction.
- Adaptive topology can improve efficiency and security while simultaneously creating a new attack surface and exposing system structure.

## Mathematical revisions

Use a dependency-aware evidence graph G=(V,E) rather than independent votes. Let each evidence item i have confidence q_i and dependency overlap d_ij. A simple research-level effective evidence weight is:

w_i = q_i / (1 + lambda * sum_j d_ij q_j).

This is not claimed as an optimal estimator; it encodes the hypothesis that correlated evidence should contribute less than independent evidence. Future work should compare this against Bayesian model averaging, Dempster-Shafer-style pooling, learned energy-based ensemble aggregation, and calibration-aware meta-learners.

For topology, optimize a vector objective rather than task accuracy alone:

J(G) = U(G) - beta C(G) - gamma K(G) - delta R(G) - epsilon A(G),

where U is useful task performance, C communication cost, K coupling/homogenization risk, R correlated-failure risk, and A attack conductivity. The weights are experimental parameters, not theoretical constants.

For regeneration, define surviving information S about a lost capability K. A necessary condition for nontrivial recovery is I(K;S)>0 unless an external source supplies information. The key experiment is to vary I(K;S) continuously and measure behavioral recovery rather than parameter similarity.

## Highest-priority falsification experiments

1. **Topology phase diagram:** sweep agent count, edge density, communication frequency, and bandwidth while holding total compute fixed; measure performance, effective diversity, calibration, and common-mode failure.
2. **Causal latent-transfer replication:** disjoint sender-private information, receiver-private controls, sender-example swaps, zeroed/random latent controls, and cross-family models.
3. **Dependency-aware fusion benchmark:** construct evidence graphs with controlled correlation and adversarial truthful fragments; compare majority vote, confidence weighting, provenance weighting, and learned energy-based pooling.
4. **Organ persistence test:** train specialists, then apply shared training/routing perturbations and measure whether causal functional identity survives; compare fixed parameter blocks with causally defined capability probes.
5. **Distributed regeneration curve:** encode a capability with controllable redundancy, destroy specialists, and measure behavioral recovery/OOD/calibration versus intact-copy and hypernetwork baselines.
6. **Topology security test:** infer the graph under black-box access, perform denial-of-collaboration attacks, and evaluate whether risk-aware edge pruning preserves useful specialization.
7. **Matched-resource novelty test:** compare the full Holobiont candidate against single-model self-conditioning, MoE, shared-backbone+adapters, ensembles, text-MAS, latent-MAS, and repair systems under matched compute, memory, communication, and parameter budgets.

## Architecture conclusion

The evidence now supports studying the Holobiont as **causally identifiable functional specialists with private state, explicit interoperability maps, adaptive selective topology, dependency-aware uncertainty/provenance, dissent-preserving evidence aggregation, distributed capability traces, and validation-gated meta-reconfiguration**.

The research does **not** yet establish that this combination is genuinely novel or superior to well-designed MoE, ensembles, model stitching, or conventional multi-agent systems. The decisive novelty test remains matched-resource causal distributed computation plus recovery under correlated and adversarial failures.
