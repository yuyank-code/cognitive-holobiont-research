# Automation Pass 11 — 2026-09-18

## Scope
Fresh pass focused on whether latent communication actually carries task-relevant information, whether collective systems can acquire distributed information, and what these results imply for Holobiont architecture. The treatise remains a hypothesis/specification.

## New evidence

### 1. Causal audits move latent communication from aggregate correlation toward mechanism
Two 2026 causal-audit studies independently intervene on relayed latent messages/KV caches rather than relying on end-task gains alone. One framework separates current-example messages, no-message, other-example messages, and receiver-self-generated messages. Another audits deranged, zeroed and moment-matched relays under receiver-private-information versus no-private-information regimes. These designs directly test whether example-specific sender content changes receiver behavior.

**Implication:** CH-003 should not be phrased as “latent communication works”; it should be phrased as a conditional causal-information-transfer claim. The relevant quantity is not message size or benchmark gain but the receiver's counterfactual dependence on sender-specific information.

### 2. HiddenBench identifies information acquisition as a separate bottleneck
HiddenBench reports a large gap between single agents with complete information and multi-agent systems where information is distributed. The failure is not simply inability to parse messages: agents often fail to recognize what other agents may know but have not communicated, causing premature convergence. Structured communication protocols improve results but do not erase the gap.

**Implication:** the Holobiont needs active information acquisition: ask/query, reveal uncertainty, request missing evidence, and maintain unresolved-information obligations. Passive broadcast is insufficient.

### 3. SILO-BENCH and MAS-BENCH provide convergent algorithmic negative evidence
Exact distributed tasks continue to show that more agents and more communication do not reliably produce distributed computation. Shared-state coordination, convention alignment, and termination are recurrent failure points. CAMOC-style metadata exchange and verification improve bounded cases.

**Implication:** the research target should be a compositional distributed algorithm with explicit state ownership, synchronization, invariants, and termination—not a generic debate architecture.

### 4. Representational and diversity collapse sharpen the independence problem
2026 committee/diversity studies report high similarity among nominally separate agents and show that dense interaction can accelerate premature convergence. Diversity-aware aggregation can help, but encoder choice and protocol details materially affect measured diversity.

**Implication:** raw model count is even less defensible as a resilience metric. The system should estimate effective independent evidence channels and test failure correlation under interventions.

### 5. Hypernetwork evidence improves generation but not resurrection
Universal Hypernetwork and SHINE-type systems show that hypernetworks can generate heterogeneous weights or LoRA adapters and transform context into parameter updates. This is strong evidence for compact capability generation/adaptation. It does not defeat the information-theoretic requirement that unique lost information must survive somewhere or be externally recoverable.

**Implication:** regeneration experiments should vary surviving information explicitly and measure capability recovery as a function of retained information.

### 6. Self-healing remains bounded repair
The 2026 Scientific Reports modular patch-layer work strengthens the baseline that damaged neural components can sometimes be repaired without full retraining. The evidence remains task-scale limited and does not establish recovery of rare or unique learned capabilities.

## Updated conceptual model

The Holobiont is now best viewed as an **information-acquisition and distributed-computation system with modular specialists**, rather than primarily a collection of communicating models:

`private specialists -> capability routing -> active information requests -> causal latent interfaces -> provenance/integrity -> dependency-aware integration -> independently grounded verification -> task anchor/termination -> distributed capability traces -> bounded repair -> validation-gated reconfiguration`

## Mathematical refinement

For receiver context `Z_R`, sender message `M_i`, task target `Y`, and receiver baseline context `X_R`, define the conditional task information:

`I_task(i) = I(Y ; M_i | X_R, Z_R)`.

This is still insufficient by itself because mutual information can reflect nuisance variables. The experimental target is therefore a counterfactual utility gap:

`Delta_i = U(Y_hat | M_i^current) - U(Y_hat | M_i^counterfactual)`

where counterfactual messages preserve marginal/message-format statistics while removing current-example sender information. A useful sender contribution must survive message-presence, other-example, self-substitution, and receiver-private-information controls.

For distributed computation, define an integration gain over a matched centralized baseline:

`G_dist = U_Holobiont - max(U_single, U_MoE, U_textMAS, U_latentMAS)`

subject to matched total compute, transmitted information, memory, and external evidence. A positive score is necessary but not sufficient: the gain must disappear when the critical private information channel is ablated, and it must persist under exact/verifiable evaluation.

For effective independence, replace agent count `N` with an empirical effective-channel measure `K_eff`, estimated from failure correlation and conditional contribution. This remains a research metric, not an established theorem.

## Contradictions strengthened

1. High latent bandwidth can coexist with weak task-relevant utility.
2. More agents can coexist with worse collective computation.
3. More communication can increase coupling and diversity collapse.
4. Hypernetwork regeneration can generate useful substitutes without recovering a uniquely erased capability.
5. Self-healing can repair behavior without preserving the original internal mechanism.

## Falsification upgrades

A Holobiont claim of genuine distributed intelligence should fail if any of the following occur under a pre-registered matched-resource protocol:

- removing one specialist's private information does not reduce performance, indicating its claimed unique contribution was unnecessary;
- self-generated receiver messages match sender-generated messages across private-information tasks, indicating no distinct distributed contribution;
- other-example message substitution preserves the claimed gain, indicating the gain was not example-specific;
- centralized/self-conditioning/MoE baselines match or exceed the Holobiont under equal information and compute;
- increasing effective independent channels does not improve reliability on tasks requiring distributed information;
- correlated component failures erase the resilience advantage;
- regeneration performance remains unchanged as surviving capability information is removed, suggesting the apparent recovery came from an external/common source;
- objective anchoring and termination do not reduce long-horizon problem drift.

## Architecture conclusion

The strongest current hypothesis is not “many AIs with a shared latent brain.” It is:

**a heterogeneous, partially independent cognitive system that actively discovers missing information, transports only causally useful state through explicit interfaces, integrates evidence with dependency awareness, verifies independently, preserves task objectives, and can repair/reconfigure itself under measurable resource and failure constraints.**

This formulation is narrower than the original treatise but substantially more falsifiable. The key unresolved novelty is still genuine distributed computation plus resilience under correlated failure, not latent communication alone.

## Sources

- SILO-BENCH, ACL 2026: https://aclanthology.org/2026.acl-long.1354/
- MAS-BENCH, Findings ACL 2026: https://aclanthology.org/2026.findings-acl.1698/
- LatentMAS, 2026: https://arxiv.org/abs/2604.15630
- StateBridge, 2026: https://arxiv.org/abs/2608.13317
- Causal audit of latent channels, 2026: https://arxiv.org/abs/2607.26773
- Causal audit of relayed KV caches, 2026: https://arxiv.org/abs/2608.04893
- Beyond tokens, 2026: https://arxiv.org/abs/2606.05711
- Diversity Collapse in Multi-Agent LLM Systems, Findings ACL 2026: https://aclanthology.org/2026.findings-acl.13/
- Universal Hypernetworks for Arbitrary Models, 2026: https://github.com/Xuanfeng-Zhou/UHN
- SHINE, 2026: https://arxiv.org/abs/2602.06358
- Self-healing neural networks, Scientific Reports 2026: https://www.nature.com/articles/s41598-026-57677-x
