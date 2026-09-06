# Contradictions and Adversarial Evidence

This is a first-class research artifact. Evidence that weakens, contradicts, or places limits on a Holobiont claim must be preserved rather than filtered out.

## Run 18 additions

### C-027 Raw agent count is a poor proxy for collective capacity
- **Claim:** More organs should produce more collective cognition.
- **Claim IDs:** CH-006/CH-021/CH-018
- **Evidence challenging it:** 2026 information-theoretic MAS scaling work reports strong diminishing returns for homogeneous agents and proposes an effective channel count K*; 2 heterogeneous agents can match or exceed many homogeneous agents in tested settings.
- **Evidence supporting the broader architecture:** Heterogeneity can preserve complementary evidence channels.
- **Current interpretation:** The relevant resource is effective independent evidence, not agent count.

### C-028 Diversity metrics can disagree with functional independence
- **Claim:** Low embedding similarity means useful specialist independence.
- **Claim IDs:** CH-006/CH-022
- **Evidence challenging it:** Representational-collapse work finds encoder choice materially changes measured similarity; BOUNDARY_SYNC finds communication effects depend on modality and group size.
- **Current interpretation:** Diversity must be triangulated across representation, behavior, failure correlation, and intervention.

### C-029 Communication can both homogenize and diversify depending on topology/group size
- **Claim:** Communication monotonically increases coupling.
- **Claim IDs:** CH-006/CH-014/CH-022
- **Evidence:** BOUNDARY_SYNC reports homogenization for some group sizes and diversification estimates for smaller groups; ACL 2026 Diversity Collapse reports dense-topology convergence.
- **Current interpretation:** Coupling is a regime variable, not a universal monotone law. The architecture needs a phase-diagram-style analysis.

### C-030 Confidence is not automatically reliable evidence
- **Claim:** Specialist confidence can be directly used for aggregation.
- **Claim IDs:** CH-009/CH-010/CH-020/CH-023
- **Evidence challenging it:** ACL 2026 multi-turn calibration work shows interaction can degrade calibration; Confident Liar reports role-dependent relationships between confidence and reasoning quality.
- **Evidence supporting it:** Diversity + calibrated confidence improves debate in controlled benchmarks.
- **Current interpretation:** Confidence must be calibrated for the interaction regime and dependency structure before being treated as epistemic weight.

### C-031 Truthful evidence fragments can form a false collective belief
- **Claim:** Evidence aggregation plus truthful messages is sufficient for collective truth.
- **Claim IDs:** CH-009/CH-010/CH-012
- **Evidence challenging it:** Lying with Truths demonstrates coordinated montage of truthful fragments can manipulate downstream beliefs.
- **Current interpretation:** Provenance and local truth are insufficient; the fusion layer must reason about composition, dependency, omission, and coalition structure.

### C-032 Hypernetwork scaling is not capability regeneration
- **Claim:** Better hypernetwork scaling closes the regeneration problem.
- **Claim IDs:** CH-007/CH-008
- **Evidence challenging it:** 2026 hypernetwork scaling laws show scalable knowledge injection, but do not demonstrate recovery after unique information is destroyed.
- **Current interpretation:** The remaining bottleneck is information preservation/distributed coding, not merely parameter generation capacity.

### C-033 Recursive memory evolution is not recursive core-model self-improvement
- **Claim:** Bounded memory/harness evolution demonstrates open-ended RSI.
- **Claim IDs:** CH-015
- **Evidence challenging it:** Recuris uses a fixed meta-agent and validation-gated skill-memory updates; this is materially narrower than unrestricted self-rewriting.
- **Current interpretation:** Bounded recursive evolution is supported; open-ended recursive architecture modification remains speculative.

## Prior contradictions retained

### C-022 Stitchability does not imply shared latent geometry
Heterogeneous models can be stitched with suitable interface training. A global shared latent space is not established as necessary.

### C-023 Specialist identity can be overwritten by shared training
Specialization can decay or be overwritten under later shared training. Organ identity should be monitored dynamically.

### C-024 More agents are not necessarily more diverse than one model
Single-model multi-output/self-conditioning remains a serious baseline and can exceed multi-agent diversity in tested tasks.

### C-025 Collective inference need not converge to consensus
Consensus-free and evidence-weighted approaches can outperform forced agreement.

### C-026 Self-repair can regenerate function without regenerating learned knowledge
Computational repair does not establish recovery of unique learned semantic capability.

### C-016 through C-021
Previous latent-causality, functional-module, behavioral-regeneration, dynamic-weight, debate-diversity, and abstention contradictions remain active and are not superseded.

## Recurring adversarial questions

1. Does consensus improve truth, or merely agreement?
2. Does redundancy remain useful when failures are correlated?
3. Does shared representation create communication or homogenization?
4. Can latent bridges transmit novel information rather than re-encode known information?
5. Can a compact generator contain enough information to reconstruct a large specialist?
6. Can uncertainty distinguish a faulty specialist from a valid unusual specialist?
7. Can truthful agents collectively construct a misleading conclusion?
8. Does regeneration preserve function, robustness, calibration, and OOD behavior?
9. Is Holobiont fundamentally novel, or a composition of existing techniques?
10. Does recursive modification improve capability without destructive drift?
11. Does effective channel count predict collective benefit better than agent count?
12. Can diversity metrics detect causal independence rather than representational distance only?
