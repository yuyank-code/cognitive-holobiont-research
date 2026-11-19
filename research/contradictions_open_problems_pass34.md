# Contradictions and Open Problems — Pass 34 (2026-11-19)

## New contradictions and cautions

### 1. Redundant topology is not independent knowledge
An alternate route can survive a downstream link failure while carrying the same upstream evidence. This is useful path redundancy, but it does not protect against corruption of the shared source, model, memory item or codec. The Holobiont must record provenance ancestry and failure domains, not only graph connectivity.

### 2. Parseable does not mean complete or true
Partial-content and semantic-corruption faults can preserve a syntactically valid message. Transport success, JSON/schema validity and receiver acceptance are separate from evidential completeness and factual correctness.

### 3. Continuous sharing can be wasteful and noisy
RCR-Router provides a peer-reviewed selective-memory baseline with lower token use and runtime than full-context sharing on its evaluated tasks. The original always-on bloodstream is therefore not the only plausible architecture and must be tested against selective access.

### 4. Structured communication is not universally sufficient
Routed Graph Handoff reports that typed graphs can compress communication but graph-only delegation regresses on a task requiring adaptive reasoning. The right design is likely hybrid and task-conditioned, not text-only or schema-only.

### 5. Model quality does not repair system-level fault handling
AgentChaos finds similar robustness rankings across tested backbones and severe drops under API faults. Upgrading the specialist may not fix truncation, routing, schema or retry failures.

### 6. Retry success is not causal recovery
Repair or Resample reports low repair rates for unguided reruns. A successful resample may be stochastic. Recovery claims require reproducible replay, failure localization, targeted intervention and independent post-repair validation.

## Open questions

1. What is the correct formal definition of an independent evidence source when models share weights, datasets, retrieval corpora, tools or prompt templates?
2. Can the system compute a provenance-aware minimum cut over information sources and failure domains?
3. What checks reliably detect semantically incomplete messages without assuming the verifier is infallible?
4. How should confidence, missingness, provenance, authorization and temporal validity be encoded in a compact organ-to-organ handoff?
5. Can latent representations preserve source lineage and uncertainty through a learned bridge?
6. Does selective context routing create hidden blind spots by withholding a relevant memory item from an organ that did not appear relevant at routing time?
7. How should routing adapt when the task itself changes after the initial delegation?
8. What level of fault injection is needed to cover model endpoint failures, network failures, semantic corruption, memory poisoning, compromised bridges and correlated source failure?
9. How can an organ distinguish a faulty peer from a peer holding rare but correct minority evidence?
10. Can recovery interventions be replayed deterministically enough to compare causal repair with stochastic resampling?
11. What is the overhead of independent evidence reacquisition, and when is it cheaper to retain a trusted replica or external log?
12. Can a persistent Narrative Thread be built as an auditable event history plus learned summary without losing temporal semantics?

## Revised architecture stance

- Keep specialist organs autonomous and heterogeneous.
- Replace unconditional full broadcast with selective, role-conditioned context routing.
- Use typed, provenance-bearing envelopes for stable dependencies and evidence contracts.
- Retain natural language for ambiguous or adaptive reasoning.
- Treat latent bridges as optional learned channels that must prove incremental value.
- Measure independent evidence sources separately from alternate network paths.
- Use stage-level fault injection and trace-based causal recovery.
- Make fresh evidence reacquisition an explicit recovery primitive.
- Preserve a last-valid event/state history so repair can replay from a trusted anchor.
