# Cognitive Holobiont — Run 22 (2026-09-11)

## Scope
Fresh literature pass focused on latent communication, effective diversity, distributed integration, MoE specialization, selection/aggregation, topology, and bounded recursive self-improvement. The treatise remains a hypothesis/specification.

## 1. Latent communication: causal evidence is stronger but sharply conditional

Two recent causal audits now provide complementary evidence. Zhang & Emu (2026), *Do Latent Channels Actually Communicate?*, intervene on sender-produced latent messages and decompose performance effects into message-presence, other-example, example-specific, and other-agent contributions. They find sender/example-specific effects in some regimes, but those components reverse or become secondary across model scale/tasks. Cheng et al. (2026), *When Does Latent Communication Pay?*, use matched, mismatched, zeroed, and moment-matched random KV controls; when receiver-private information is genuinely needed, matched relays can dominate irrelevant relays, while in receiver-nonprivate regimes effects can be statistically equivalent. This materially strengthens the causal standard while weakening universal claims.

**Revision:** CH-003 remains Partially supported, but the operative quantity should be conditional sender-specific information gain under receiver isolation, not aggregate accuracy lift.

## 2. Effective diversity has a promising information-theoretic formulation

Yang et al. (2026), *Understanding Agent Scaling in LLM-Based Multi-Agent Systems via Diversity*, argues that homogeneous scaling saturates because outputs are correlated and introduces K* as an effective channel count. The result that a small heterogeneous team can match much larger homogeneous groups supports replacing raw agent count with effective independent evidence.

**Caution:** K* is not yet established as a causal or universal measure of cognitive independence. It must be tested against controlled common-mode failures, representation-independent behavioral measures, and matched single-model multi-output baselines.

## 3. Selection is emerging as a bottleneck distinct from generation diversity

The 2026 *Selection Bottleneck* study reports that heterogeneous teams can outperform single models under strong judge-based selection, while homogeneous Self-MoA can win under weaker synthesis. Independent judging attenuates the headline effects substantially, so the result should not be treated as settled. The important architectural insight is more robust: **diversity is only useful if the integration/selection mechanism can exploit it.**

This complements SILO-BENCH: acquisition and candidate generation are separable from correct integration.

## 4. Distributed computation remains the central negative result

SILO-BENCH (ACL 2026) tests 1,620 configurations and finds active communication with severe failures in integrating distributed state. MAS-BENCH independently finds sharp degradation on distributed sorting as agent count grows. ALEM adds open-ended long-horizon evidence that current LLM agents remain far from reliable scalable coordination.

**Revision:** CH-006/CH-025 should emphasize an explicit integration operator/state representation. A communication network is not itself a distributed computer.

## 5. MoE specialization: routing is not organ identity

The 2026 *Expert Collapse and Compositional Failure in Simple Multimodal MoE* work finds forced specialization can be overwritten by later multimodal training. New theoretical work argues router specialization largely reflects hidden-state geometry rather than semantically meaningful expert domains. This reinforces the longitudinal causal-organ definition.

**Revision:** a specialist must retain intervention-sensitive functional identity after continued training and routing perturbation. Routing entropy or expert labels alone are insufficient.

## 6. Model stitching supports interfaces, not one common mind-space

The 2026 foundation-model stitching study shows heterogeneous VFMs can be stitched, but stitch depth and training objective strongly affect success. Deep feature-matching interfaces can outperform constituent models in some settings. This supports explicit interface maps and argues against requiring one universal shared latent geometry.

## 7. Topology is now a first-class causal variable

Recent work on topological collapse reports hub dominance and loss of higher-order interactions in large agent societies. Other scaling work finds intermediate communication complexity can be best, with consistency becoming a major failure mode. These results support treating topology as a controlled resource with utility, coupling, attack-conductivity, and common-mode-failure costs.

## 8. Byzantine robustness still does not solve epistemic truth

SAC and CP-WBFT report improved suppression of Byzantine influence under strong adversarial conditions. This is valuable fault containment evidence, but it does not protect against honest agents sharing the same wrong source, specification error, or correlated hallucination. The immune-system target remains dependency-aware evidence reliability rather than majority agreement.

## 9. Recursive self-improvement: bounded memory evolution remains the strongest evidence

Recuris provides recent evidence for validation-gated evolution of working/skill memory under a fixed meta-agent. New self-referential introspection work argues that sustainable RSI may require a threshold of self-modeling. Neither establishes unrestricted recursive rewriting of the core learner. The architecture conclusion remains stable: first investigate stable meta-processes that modify memory, routing, policies, and repair strategies.

## 10. Updated synthesis

The strongest current Holobiont formulation is now:

> heterogeneous, causally identifiable specialists with private internal representations; sparse/adaptive interface-mediated communication; sender-specific information tests; dependency-aware evidence fusion/selection; distributed memory and capability traces; common-mode-failure detection; behavior-level regeneration; calibrated abstention; and bounded meta-reconfiguration.

The novelty test remains strict: beat single-model multi-output/self-conditioning, MoE, shared-backbone+adapters, ensembles, conventional MAS, and repair/regeneration baselines under matched compute, memory, communication, information, training-data, and redundancy budgets.

## New literature anchors

- Zhang & Emu (2026), arXiv:2607.26773 — causal audit of latent channels.
- Cheng et al. (2026), arXiv:2608.04893 — causal audit of relayed KV caches.
- Yang et al. (2026), arXiv:2602.03794 — effective channel count K* and diversity scaling.
- Cui et al. (2026), Findings ACL — single-agent multi-output vs MAS diversity.
- Zhang et al. (2026), ACL — SILO-BENCH distributed coordination.
- MAS-BENCH (2026), Findings ACL — distributed sorting failure under scaling.
- Mai et al. (2026), arXiv:2603.12433 — heterogeneous foundation-model stitching.
- Ticinovic & Han (2026), PMLR 332 — expert collapse/compositional failure.
- Lee et al. (2026), arXiv:2605.09076 — Byzantine-resilient LLM MAS.
- Yu et al. (2026), arXiv:2608.24876 — recursive experiential-working memory evolution.
