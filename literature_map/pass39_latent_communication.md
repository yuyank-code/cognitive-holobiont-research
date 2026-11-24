# Living Literature Map — Pass 39: Latent Communication and Connective Tissue
**Date:** 2026-11-24

## Cluster A — Causal proof that a payload carries example-specific content
- Zhang & Emu, arXiv:2607.26773: current-example vs other-example vs no-message vs receiver-self-generated audit.
- Cheng, Das & Ramnath, arXiv:2608.04893: true/deranged/zero/random cache audit under receiver-necessity and natural-task regimes.

**Current synthesis:** A latent payload can carry example-specific content, but a benchmark delta or message-presence effect does not prove that. Receiver necessity and matched derangement controls are essential.

## Cluster B — Cross-model alignment
- Chen et al., arXiv:2606.13594v2: dense KV alignment, Qwen size pairs, Mistral-to-Qwen transfer and three-agent document sharing.
- Piepereit, arXiv:2608.16347: activation projection and injection; end-to-end transfer is architecture-dependent and only one of three decoder-only pairs passes the reported causal criterion.
- HyLaT, EMNLP 2026: per-agent adapters in a small Llama/Qwen heterogeneous variant.

**Current synthesis:** Pair-specific interoperability is feasible; global architecture-independent latent geometry is not established.

## Cluster C — Compression and efficiency
- LatCom, EMNLP 2026: joint multi-sender compression to fixed receiver-readable slots; same-family Qwen3 setup; lower token use and latency with comparable accuracy.
- HyLaT, EMNLP 2026: dual-channel latent/text protocol, multi-round interactions and text compatibility.

**Current synthesis:** The connective tissue should select channel and compression according to task and receiver context. Full relay may be useful for fine-grained detail; compression may be preferable when sender trajectories are redundant.

## Cluster D — Homogenization and diversity retention
- BOUNDARY_SYNC, arXiv:2607.01600: communication-induced output coupling, with methodological caveats.
- Pass 38 effective-organ independence literature remains relevant.

**Open gap:** Measure task-specific error correlation and unique capability retention before/after repeated communication in genuinely heterogeneous specialist populations.

## Cluster E — Security, provenance and privacy
- Brito & Baquero, arXiv:2606.28958: KV integrity, visible commitment mismatch and HMAC-based post-handoff transport authentication.
- Beyond Tokens, arXiv:2606.05711: taxonomy identifies cross-architecture alignment and latent-channel security as open problems.

**Current synthesis:** Transport integrity and endpoint semantic trust are separate. Text verification cannot inspect hidden payload semantics. Privacy leakage from latent caches needs direct measurement.

## Cluster F — Older foundational work to retain
- CIPHER / Let Models Speak Ciphers (ICLR 2024).
- LatentMAS (ICML 2026).
- Interlat (ACL 2026).
- Cache-to-Cache and KVComm.
- Thought Communication and State Delta Trajectory.

## Next literature gaps
- Independent replication of causal mismatched-cache audits.
- Cross-modal transfer (vision/audio to language and action) with private-evidence controls.
- Long-horizon multi-round use with real serving systems.
- Latent payload privacy/reconstruction and endpoint-compromise defenses.
- Adaptive bandwidth and receiver-requested detail.
- Adapter version drift and model replacement.
