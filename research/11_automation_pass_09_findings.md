# Automation Pass 09 — 2026-09-01

## Scope
This pass focused on the strongest unresolved claims from Pass 08: causal novel-information transfer in latent communication, common-mode failure under redundancy, Byzantine aggregation, and the scalability of hypernetwork regeneration/self-modification.

## 1. Major new evidence: causal audit weakens the naive latent-communication claim

A July 2026 preprint, *Do Latent Channels Actually Communicate? A Causal Audit of Latent Multi-Agent LLM*, argues that end-task gains alone cannot establish that a receiver uses task-relevant sender information. It introduces controlled message replacement and decomposes performance effects into message-presence, example-specific content, and additional agent value. Results on Qwen3-4B/8B and GSM8K/ARC-C/MATH-500 show that aggregate gains can be dominated by information that is not specific to the evaluated example; the balance differs by model and task. The paper therefore provides direct methodological evidence against treating benchmark improvement as proof of novel information transfer.

Status change: CH-003 should be treated as **unresolved / weakly supported**, not as straightforward partial confirmation. The strongest remaining requirement is a preregistered causal test with post-training sender-only facts and receiver-isolation controls.

A separate 2026 preprint, *Latent Communication Between Language Model Agents: Channels, Alignment, and the Limits of Text*, reports that latent channels can preserve more probe-detectable features than text under heavy compression, but on its tested cross-lingual concept tasks the latent channel did not outperform text, and the authors conclude that many features lost by text serialization appear to encode surface form rather than task-relevant semantics. This is an important negative result: latent bandwidth alone does not imply a cognitive advantage.

## 2. Latent communication is now a mature-enough subfield to require standardized causal evaluation

ACL 2026 Interlat formally demonstrates entirely latent inter-agent communication and reports heterogeneous-model gains plus large compression/inference benefits. A 2026 survey organizes eighteen methods across embeddings, hidden states, KV-caches, alignment, and fusion. These establish feasibility and a growing design space, but the causal-audit and negative-result papers show that feasibility and benchmark improvement are insufficient evidence for the strongest Holobiont claim.

Updated conclusion: latent communication is **strongly supported as an engineering mechanism**, while genuinely novel task-relevant information transfer remains **unresolved**.

## 3. Common-mode failure: diversity helps, but specification/common-cause errors remain

The 2026 arXiv paper *N-Version Programming with Coding Agents* evaluates 48 implementations produced from 69 agent/model/language configurations on one million randomized tests. It reports substantial co-failure across otherwise diverse systems, including failures attributable to shared specification misunderstandings. Yet three-version majority units reduce mean observed failures from 387.44 to 130.99, demonstrating that redundancy can still help under correlated failures.

The data are publicly archived on Zenodo, which makes this a useful reproducibility target. The paper should not be interpreted as proving statistical independence: it explicitly finds common-mode failure. Its strongest lesson for the Holobiont is that diversity must be engineered at the level of causal failure mechanisms, not merely model identity, language, or parameter distance.

Updated conclusion: CH-011 remains strongly supported in bounded settings; CH-012 is strengthened as a first-order constraint. A future Holobiont benchmark should inject failures at shared-data, shared-specification, shared-backbone, shared-memory, routing, and repair-generator levels independently.

## 4. Byzantine coordination: protocol structure can materially improve resilience

AAAI 2026 *Rethinking the Reliability of Multi-agent System: A Perspective from Byzantine Fault Tolerance* reports a confidence-probe weighted BFT mechanism (CP-WBFT) that improves reliability in tested topologies under extreme Byzantine conditions, with experiments reporting performance at an 85.7% fault rate.

A separate 2026 preprint, *Robust Multi-Agent LLMs under Byzantine Faults*, proposes Self-Anchored Consensus (SAC), a decentralized filter-and-refine protocol with graph robustness conditions, reporting suppression of Byzantine influence on mathematical and commonsense benchmarks.

Conversely, *Byzantine Cheap Talk* reports that adversarial signaling can exploit coordination-game dynamics and that communication topology itself can affect cooperation. *Resilient Consensus in Agentic AI* finds that prompted LLM agents can fail to reach agreement even where classical consensus theory would permit convergence, while external resilient filters improve agreement.

Synthesis: protocol-mediated resilience is increasingly supported, but **agreement remains distinct from truth**. The Holobiont immune layer should retain provenance, confidence, disagreement, and reliability history rather than collapse evidence into a single majority decision.

## 5. Hypernetwork evidence: stronger for generation, still weak for recovery

*Universal Hypernetworks for Arbitrary Models* (2026) reports a fixed generator conditioned on parameter, architecture, and task descriptors that can instantiate heterogeneous target models across tested vision, graph, text, and regression settings, including recursive generation through intermediate hypernetworks.

This strengthens CH-007: compact generators can parameterize heterogeneous specialists and the generator need not be rebuilt for every target architecture in the tested regime.

However, this is still not evidence for lossless recovery of a destroyed specialist. The critical missing test is whether a generated replacement preserves rare capabilities, calibration, OOD behavior, long-tail knowledge, and idiosyncratic skills that are absent from the surviving system.

Text-to-LoRA and related hypernetwork-generated adaptation work further support compact specialization, but adapters remain a weaker target than complete specialist reconstruction.

## 6. Recursive self-modification: technical feasibility is advancing, general self-rearchitecture is not established

*Hypernetworks That Evolve Themselves* embeds variation/inheritance machinery inside self-referential graph hypernetworks and demonstrates adaptive evolution on RL environments. This supports bounded self-modification and evolvability mechanisms.

It does not establish safe general architectural self-rewrite, monotonic improvement, or preservation of prior capabilities across many generations. The Holobiont claim should therefore remain speculative at the full-system level.

## 7. Revised architecture hypothesis

The evidence now favors a layered design hypothesis:

- private specialist representations;
- a learned interoperable communication interface rather than a single forced latent geometry;
- explicit epistemic metadata/provenance alongside cognitive latent messages;
- reliability-aware aggregation that preserves disagreement;
- distributed memory/evidence;
- capability-level repair/regeneration;
- controlled rather than unrestricted self-reconfiguration.

This is still only a hypothesis. Its novelty must be demonstrated against MoE, shared-backbone+adapters, ensembles, ordinary multi-agent systems, hypernetwork regeneration, and repair baselines at matched resources.

## 8. New falsification backlog

1. **Causal latent novelty test:** introduce a fact to sender only after receiver training; compare latent, text, randomized-message, other-example-message, and no-message conditions; require receiver recovery of the sender-only fact.
2. **Latent-vs-text matched-bandwidth test:** equalize bits, latency, and compute before comparing channels.
3. **Common-cause diversity matrix:** independently vary shared weights, training data, prompts/specification, memory, routing, repair generator, and evaluator; measure pairwise and higher-order failure correlation.
4. **Epistemic aggregation test:** compare majority vote, confidence-weighted consensus, provenance-aware aggregation, and Byzantine filtering under colluding specialists and useful minority evidence.
5. **Unique-capability regeneration test:** destroy a specialist whose rare capability is not present in survivors; measure whether hypernetwork, adapter, distributed reconstruction, and Holobiont recovery preserve the capability.
6. **Recursive retention test:** permit repeated self-modification while evaluating a fixed historical capability suite with held-out evaluators; reject any claim of improvement that trades away prior capabilities without explicit accounting.

## Net assessment
The research is becoming more conservative about the strongest claims while simultaneously strengthening the case for several component mechanisms. The most important new evidence this pass is the causal-audit literature: **latent communication should no longer be credited with genuine novel information transfer merely because aggregate benchmark accuracy improves.** The central Holobiont problem is now better defined as joint optimization of information gain, diversity, common-mode resilience, repair fidelity, and reconfiguration stability.
