# Architecture Note — Pass 39
## Auditable Hybrid Connective Tissue
**Date:** 2026-11-24

## Design objective
Preserve the Treatise's ambition for richer-than-text communication without assuming every organ should expose all internal state or that all latent spaces share a universal geometry.

## Proposed edge object
Each directed organ-to-organ edge is configured by a pair-specific communication contract:

- sender identity, model/checkpoint hash and adapter/codec version;
- receiver identity and compatible model version;
- task/episode/session identifier;
- source evidence identifiers, provenance and authorization scope;
- receiver-context regime: shared input, partial overlap or private sender-only evidence;
- payload kind: typed record, text, embedding, hidden state, KV cache or hybrid;
- tensor metadata, dimensions, sequence length, dtype and position convention;
- payload digest and authenticated transport manifest;
- visible concise commitment, uncertainty, freshness and expiry;
- fallback route and fail-closed behavior.

## Data plane and control plane
**Data plane:** latent payloads or structured evidence used for machine-to-machine transfer.

**Control plane:** inspectable metadata, commitments, provenance, permissions, task scope, freshness, integrity status and error/fallback records.

A valid control-plane record does not certify semantic truth. It makes the payload traceable and the transport auditable.

## Routing policy
1. Keep local organ state private by default.
2. Ask whether the receiver lacks evidence or capability that the sender uniquely holds.
3. If not, use no communication or a cheap typed summary unless measured utility justifies more.
4. If yes, choose among text, typed evidence, native KV, pair-specific adapter, compressed latent or hybrid channel using held-out measurements.
5. Prefer hybrid for multi-round operation when decisions and commitments need to remain inspectable.
6. Authenticate and version the payload before receiver injection.
7. Reject stale, wrong-model, wrong-session or tampered payloads.
8. If a latent path fails, downgrade to verified text/typed evidence or abstain; do not silently accept an unverified tensor.
9. Monitor response diversity and correlated errors after communication.

## Trust boundaries
- **Transport authenticity:** did the payload arrive unchanged from the claimed sender/session?
- **Endpoint integrity:** was the sender runtime/model compromised?
- **Semantic validity:** does the payload accurately reflect evidence and task context?
- **Authorization:** may this organ disclose or use this evidence for this receiver/task?
- **Freshness:** is the state still valid for the current episode?

These are separate checks. HMAC/signature protects only the declared transport boundary under uncompromised keys.

## Versioning and replacement
Every bridge is directed and versioned (sender version → receiver version). A model update invalidates the assumption that the old adapter remains valid. Run a compatibility suite before re-enabling the edge. Keep a typed/text fallback during migration.

## Why not a universal latent bloodstream?
- Model spaces and KV conventions are not universally aligned.
- Dense payloads can be orders of magnitude larger than text.
- Current evidence is bounded to small numbers of agents and selected model pairs.
- Opaque state increases semantic auditing and privacy difficulty.
- Continuous broadcasting can waste compute and reduce specialist diversity.

The near-term target is selective, pair-specific, auditable interoperability, not universal telepathy.
