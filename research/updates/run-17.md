# Research Update 17 — 2026-09-06

## Substantive findings

### 1. The "organ" problem is now coupled to representation compatibility
The 2026 model-stitching study revisiting heterogeneous vision foundation models finds that heterogeneous models can be stitched reliably, but stitch-layer training objective and depth matter substantially. Deep stitches can outperform either constituent model in tested tasks, while shallow stitching can fail under conventional feature-matching/task-loss procedures.

**Revision:** CH-002/CH-004 remain strongly supported for interoperability, but stitching is not evidence that two specialists share a common cognitive geometry. Compatibility can be learned at selected interfaces. The Holobiont should therefore prefer explicit interface contracts over assuming globally aligned latent spaces.

### 2. MoE expert collapse is a direct warning about specialist stability
PMLR 2026 work on multimodal MoE finds that forced unimodal specialization can be overwritten by subsequent multimodal training, with the latent space reverting toward modality clustering. A separate 2026 MoE preprint proposes disentanglement to reduce expert collapse, reinforcing that specialization is a controllable property rather than an automatic consequence of having multiple experts.

**Revision:** CH-005 is downgraded in generality. Shared training can erase useful specialization. Specialist identity must be continuously measured behaviorally/causally rather than inferred from routing statistics.

### 3. The communication–diversity tension has independent ACL evidence
ACL 2026 Diversity Collapse reports diminishing diversity with group scaling and faster convergence under dense communication. ACL 2026 Single-Agent Generation Surpasses Multi-Agent Systems independently shows that a single model producing multiple conditioned outputs can exceed multi-agent systems in semantic diversity on matched divergent-thinking tasks.

**Revision:** the Holobiont must beat both multi-agent and single-agent multi-output baselines. "More organs" is no longer a defensible proxy for more diversity.

### 4. Consensus is not the only or necessarily preferred aggregation primitive
ACL 2026 Free-MAD explicitly removes consensus, using trajectory-level scoring and anti-conformity; it reports gains over conventional debate on eight benchmarks. ACL 2026 Demystifying Multi-Agent Debate separately finds that initial diversity and calibrated confidence are the mechanisms that improve debate.

**Revision:** CH-010 should be formulated as **evidence-weighted collective inference**, not consensus. Candidate hypotheses, confidence, provenance, and dissent should survive until the commitment step.

### 5. Recursive self-improvement is gaining evidence for bounded memory evolution
Recuris (arXiv 2608.24876, Aug. 25 2026) uses a fixed meta-agent to make validation-gated localized updates to skill memory from execution evidence. It reports improvements on 35 of 37 completed model-benchmark pairs across four long-horizon benchmarks and ten models.

**Revision:** CH-015 becomes stronger for **bounded recursive memory/harness evolution**, but this remains distinct from recursive rewriting of the core learner. The stable-meta-process hypothesis is now a serious candidate architecture.

### 6. Biological self-repair is becoming mechanistically informative, but not proof of cognition
Self-Organising Digital Circuits demonstrate functional logic regeneration and rerouting around unseen hardware faults, including >99.99% soft-error recovery in tested regimes. A separate GNCA study finds structured internal fluctuations and distributed redundancy changes during damage recovery.

**Revision:** biological analogy now has a stronger mechanistic analogue: regeneration can emerge from local rules plus distributed state. But this still establishes repair of a computational function, not regeneration of a unique cognitive capability or consciousness.

### 7. Byzantine defenses remain useful but should be treated as filters, not truth oracles
AAAI 2026 CP-WBFT reports improved reliability under extreme tested Byzantine rates; Self-Anchored Consensus reports suppression of Byzantine influence. However, debate/consensus work continues to show conformity and identity-driven bias. The combined evidence supports a layered reliability mechanism rather than a single consensus rule.

**Revision:** CH-009/CH-012 should emphasize provenance, confidence, correlation estimates, and abstention in addition to Byzantine filtering.

## New mathematics

### Interface compatibility versus shared geometry
Let z_j be a specialist's private representation and T_ji an interface map into receiver i's admissible input space. Require task-level utility U(T_ji(z_j)) without requiring d(z_j,z_i) to be small or globally meaningful. This separates interoperability from representation identity.

### Functional diversity
For specialists j,k define failure correlation rho_jk over a preregistered perturbation set P:

rho_jk = Corr( L_j(P), L_k(P) )

where L is a vector of behavioral failures rather than scalar accuracy. A useful diversity measure should aggregate low failure correlation across targeted perturbation families, not weight distance alone.

### Communication-constrained collective objective
J = A - lambda_B B - lambda_C C + alpha D_cap + beta D_epi - mu R_corr

where B is latent bandwidth, C coordination cost, D_cap capability diversity, D_epi epistemic diversity, and R_corr correlated-failure risk. The research program should report Pareto frontiers rather than selecting arbitrary coefficients.

### Regeneration information lower bound
If unique capability information K is absent from all surviving state S, external memory M, generator G, and observations O, then any recovery mechanism R(S,M,G,O) cannot reliably reconstruct K beyond information already present in those variables. The empirical question is therefore distributed coding: how much unique capability can be redundantly encoded at a given storage/communication overhead?

## Updated claim statuses

- CH-002 latent bridges: **Strongly supported for bounded interoperability**; not equivalent to shared cognition.
- CH-005 high shared-parameter ratio preserves specialization: **Partially supported, with stronger evidence that specialization can be overwritten**.
- CH-006 continuous communication preserves specialization: **Plausible but conditional; dense communication has direct counterevidence**.
- CH-010 consensus/debate improves truth: **Partially supported only as evidence-weighted inference; consensus itself is not the mechanism**.
- CH-011 redundancy: **Strongly supported in bounded settings**.
- CH-012 common-mode control: **Open / weakly supported**.
- CH-015 recursive self-rearchitecture: **Partially supported for bounded memory/harness evolution; speculative for core self-rewrite**.
- CH-018 full-system novelty: **Open**.

## New contradiction log items

1. Heterogeneous models can be stitchable without sharing one latent geometry; therefore shared representation is not a prerequisite for interoperability.
2. MoE experts can specialize and later lose that specialization under shared multimodal training; therefore specialist identity is dynamically fragile.
3. Single-agent multi-output can outperform MAS on diversity; therefore multi-agent structure is not inherently diversity-producing.
4. Consensus-free debate can outperform consensus-based debate; therefore collective intelligence need not terminate in agreement.
5. Self-organising circuits can regenerate function after unseen faults; therefore neural self-repair is feasible, but this is not evidence for recovery of unique learned knowledge.

## New falsification priorities

1. **Stitching-vs-shared-latent experiment:** compare explicit interface maps, forced common latent spaces, and no-bridge baselines at matched bandwidth.
2. **Specialization half-life test:** measure how quickly private specialist capabilities decay under shared training, memory sharing, and communication.
3. **Single-agent-vs-Holobiont diversity benchmark:** matched compute, identical prompt budget, multi-output single model versus independent specialists versus interacting specialists.
4. **Consensus-free epistemic aggregation:** compare majority, confidence-weighted, provenance-weighted, anti-conformity, and abstention-aware aggregation under correlated/colluding errors.
5. **Distributed regeneration coding experiment:** destroy a specialist and vary redundancy rate to estimate the storage/communication threshold at which capability becomes recoverable.
6. **Bounded recursive-memory longevity test:** iterate Recuris-like updates for many generations and measure retained capabilities, regression, and diversity.
7. **Repair-vs-regeneration test:** compare self-organising functional repair against learned-knowledge regeneration under identical fault budgets.

## Architecture conclusion

The preferred architecture is now best described as **functionally modular rather than parameter-modular**. Specialists retain private representations and are connected through explicit, sparse, auditable interface maps. Collective inference preserves multiple hypotheses, confidence, provenance, and abstention. A distributed capability code provides recoverability rather than relying on magical regeneration. A stable meta-process may evolve memory, routing, interfaces, and repair policies while leaving the core learner comparatively protected.

The decisive novelty criterion remains a matched-resource demonstration of a capability or resilience property that cannot be reproduced by a single-model multi-output system, MoE, ensemble, conventional text-MAS, latent-MAS, or standard self-healing baseline.

## Key sources

- Revisiting Model Stitching In the Foundation Model Era — arXiv:2603.12433.
- Expert Collapse and Compositional Failure in Simple Multimodal MoE — PMLR 332, 2026.
- Diversity Collapse in Multi-Agent LLM Systems — Findings ACL 2026.
- Single-Agent Generation Surpasses Multi-Agent Systems in Semantic Diversity — Findings ACL 2026.
- Demystifying Multi-Agent Debate — Findings ACL 2026.
- Free-MAD: Consensus-Free Multi-Agent Debate — Findings ACL 2026.
- Recuris: Recursive Experiential-Working Memory Evolution — arXiv:2608.24876.
- Self-Organising Digital Circuits — arXiv:2608.02606.
- Structured Fluctuations and the Information Dynamics of Self-Maintenance in Growing Neural Cellular Automata — arXiv:2607.12403.
- CP-WBFT / Rethinking the Reliability of Multi-agent System — AAAI 2026.

No implementation was started. Evidence remains provisional where based on recent preprints.