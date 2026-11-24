# Contradictions and Open Problems — Pass 39
**Date:** 2026-11-24

## Contradictions and tensions

1. **High channel capacity vs. actual task use.** A hidden-state tensor may encode much information, yet the receiver may ignore example-specific content or benefit only from a generic prefix/interface effect.
2. **Latent transfer vs. receiver redundancy.** Native KV relay can carry private evidence when needed, but natural benchmark gains can have negligible pairing effects when the receiver already has sufficient information.
3. **Representation alignment vs. causal transfer.** Cross-model probes and similarity metrics can be positive while activation injection has no measurable generation-level effect.
4. **Dense fidelity vs. communication efficiency.** Full KV relay may preserve fine detail; fixed-slot compression reduces cost but can discard useful information on some tasks.
5. **Efficiency vs. portability.** Pair-specific adapters can bridge models, but each new model/checkpoint pair may require training, validation and maintenance.
6. **Opaque richness vs. auditability.** Latent messages may preserve internal state unavailable in text, but their content is difficult for external verifiers to inspect.
7. **Hybrid compatibility vs. latent opacity.** Text commitments improve interoperability and observability, but they do not reveal whether the latent payload is semantically aligned with the text.
8. **Communication vs. specialist diversity.** Peer communication may help integrate evidence while also causing output homogenization; current coupling measurements have task and protocol confounds.
9. **Transport integrity vs. endpoint truthfulness.** HMAC can detect post-handoff alteration under key assumptions; it cannot certify that a specialist signed a truthful or safe representation.
10. **FLOP/token savings vs. deployment cost.** Avoiding text generation may reduce model compute, but KV payloads can be megabytes and transport/storage/adapter costs are often omitted.

## Open questions

### Causal information transfer
- Does a latent channel carry answer-relevant, example-specific information when the receiver has no source input?
- How much of the gain survives a compute-matched self-generated receiver message?
- Which sender message components/layers/groups carry the useful evidence?
- Does transfer survive sender/receiver role swaps and model version changes?
- Are current-example gains robust on human-authored evidence rather than constructed registries?

### Heterogeneous interoperability
- What is the smallest useful adapter for each model pair?
- Can adapters generalize across checkpoints, quantization, tokenizer revisions, context lengths and instruction tuning?
- Does a shared interface preserve private specialist representations better than joint latent-space training?
- How do modality-specific organs (vision/audio/code) communicate with language-centric receivers?

### Compression and routing
- Should compression budget scale with receiver uncertainty, evidence novelty, source reliability and task difficulty?
- Can a receiver request additional latent detail selectively?
- Can the system jointly compress complementary evidence without suppressing minority evidence?
- When is a typed evidence graph better than latent slots?

### Security and governance
- Can endpoint-signed malicious payloads be detected semantically?
- How should latent payloads be authenticated, versioned, expired and revoked?
- What privacy leakage is possible from shared KV caches or embeddings?
- Can the receiver verify a latent payload's provenance and relation to the visible commitment without trusting the sender?
- What fallback is safe when an adapter, codec or model family is compromised?

### Long-horizon Holobiont relevance
- Does a hybrid connective tissue improve persistent memory, fault recovery and self-reconfiguration, not merely short QA?
- Does repeated latent exchange cause representational or behavioral homogenization?
- Can a federation retain distinct expertise while still learning shared protocols?
- Does the benefit survive matched compute, bandwidth, latency, memory, information and verifier budgets?

## Contradiction log policy
Do not resolve these tensions by selecting the most positive paper. Maintain separate entries for (a) encoded information, (b) receiver sensitivity, (c) example-specific task utility, (d) separate-agent marginal value, (e) deployment efficiency, and (f) security/privacy.
