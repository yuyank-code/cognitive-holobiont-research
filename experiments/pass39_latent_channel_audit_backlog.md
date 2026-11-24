# Experiment Backlog — Pass 39
**Date:** 2026-11-24  
**Priority:** Establish causal latent transfer before implementing a continuous latent bloodstream.

## Experiment 1 — Receiver-necessity × channel matrix
**Question:** Does the receiver use sender-specific information, and under what context regime?

Regimes:
A. Receiver already sees the sender's source input.
B. Receiver lacks sender-private evidence.
C. Receiver has partial overlapping context and must combine multiple private observations.

Arms:
- no communication;
- text;
- typed structured evidence;
- native KV relay;
- learned cross-model KV/activation bridge;
- compressed multi-sender latent relay;
- hybrid latent-text protocol;
- receiver self-generation with matched compute.

Controls:
- current-example vs deranged/mismatched payload;
- intact-format answer-irrelevant payload;
- zero and moment-matched random payload;
- matched self-generated receiver message;
- sender ablation and ownership swaps.

Primary metrics: τ_pair, τ_private, CAG, SSG, exact match/F1 or task-specific verified utility.

## Experiment 2 — Cross-model bridge generalization
Test at least three directed model-family pairs, including size asymmetry and tokenizer/architecture differences. Train each adapter only on designated training tasks. Hold out model versions, task families and evidence formats. Compare:
- learned KV adapter;
- activation projection;
- shared-space adapter;
- typed evidence graph;
- hybrid latent-text;
- text-only baseline.

Record adapter training/maintenance compute, payload bytes, peak memory, receiver compute, and wall-clock latency. A bridge that only works for one checkpoint pair should be recorded as pair-specific, not general.

## Experiment 3 — Latent compression and information loss
Compare full relay, independent per-sender compression, joint multi-sender compression, adaptive slot budget and text/typed summary. Include code tasks where full relay may preserve fine detail. Measure evidence recall, minority-evidence preservation, error propagation and downstream utility, not only token count.

## Experiment 4 — Multi-round specialist diversity
Measure response distributions, error correlation and capability retention before and after repeated communication. Use no-communication, staged sharing, continuous consensus and hybrid controls. Include task families beyond QA/debate. Do not treat one coupling metric as a universal measure of diversity.

## Experiment 5 — Integrity, provenance and fallback
Attack the transport boundary with payload substitution, replay, stale session identifiers, model/codec mismatch, metadata forgery and truncation. Separately test malicious endpoints that sign their own payloads. Verify:
- HMAC/signature validation;
- fail-closed behavior;
- text/typed-evidence downgrade;
- source-to-payload manifest binding;
- no acceptance of stale or wrong-model cache state.

Report transport tamper detection separately from endpoint semantic-malice detection.

## Experiment 6 — Privacy and information leakage
Test whether embeddings/KV payloads permit reconstruction or inference of private source evidence. Measure leakage under the intended threat model and evaluate whether redaction, encryption at rest/in transit, access controls or selective disclosure change utility.

## Statistical and resource protocol
- Pre-register primary outcomes, practical-equivalence margins and exclusions.
- Use paired example-level comparisons and multiple independent seeds.
- Use held-out tasks and fresh private facts to avoid receiver memorization.
- Report confidence intervals and equivalence tests for null effects.
- Count total model compute, adapter training, network bytes, storage, memory, latency and verification cost.
- Keep the external evaluator independent of the latent adapter training pipeline.
