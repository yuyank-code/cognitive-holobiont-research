# Claim–Evidence Matrix Addendum — Pass 39
**Date:** 2026-11-24  
**Topic:** Latent communication and connective tissue.

| Claim from the Treatise / hypothesis | New external evidence | Status after Pass 39 | Main limitation / decisive next test |
|---|---|---|---|
| Hidden representations can carry more than visible text between organs. | Native KV relay transmits sender-private content in calibrated receiver-necessity tests (Cheng et al., preprint); cross-family KV alignment works for selected Mistral→Qwen and Qwen size pairs (Chen et al., preprint). | **Conditionally supported** | Replicate across additional families, tasks, modalities and independent teams. |
| A benchmark gain proves the receiver used the sender's example-specific content. | Causal audits find true-vs-deranged effects can be near zero on natural tasks despite true-vs-zero cache gains; current-example effects can differ from self-generated receiver value (Zhang & Emu; Cheng et al., preprints). | **Contradicted as a general inference rule** | Require mismatched-content and compute-matched self-substitution controls. |
| Latent relay is most useful when organs hold complementary private information. | Calibrated split-evidence tests show near-ceiling true-cache transfer versus answer-irrelevant cache; three-agent document-memory tests report gains over text and receiver-only baselines. | **Supported in bounded settings** | Test realistic, non-synthetic evidence, multi-step actions and held-out domains. |
| Any learned bridge can make heterogeneous latent spaces interoperable. | Cross-family KV alignment and HyLaT adapters show selected pairwise transfer; activation projection succeeds end-to-end for only one of three decoder-only pairs in another preprint. | **Conditional; universal form unsupported** | New model pairs, model updates, tokenizer/architecture changes, held-out tasks. |
| A single latent channel is best for all communication. | Peer-reviewed HyLaT supports a hybrid latent-plus-text protocol; LatCom supports fixed-slot multi-sender compression but remains same-family. | **Not supported** | Compare hybrid, structured text, native KV and compressed bridges under full cost accounting. |
| More latent bandwidth is always better. | LatCom finds cross-agent redundancy and reduces multi-sender latents to fixed slots; its fixed budget loses to full relay on some code tasks. | **Contradicted as a general rule** | Adaptive budget by task and evidence novelty; ablate compression on high-detail tasks. |
| Latent messages preserve independent specialist diversity. | BOUNDARY_SYNC preprint reports communication-induced homogenization, with significant methodological confounds. | **Open / risk identified** | Measure task-specific error correlation and capability retention before/after communication. |
| A visible commitment can validate a hidden payload. | When Latent Agents Lie shows visible text checks miss malicious KV changes; HMAC protects post-handoff integrity but not endpoint truthfulness. | **Contradicted** | Separate transport authentication, endpoint trust and semantic evidence validation. |
| A latent channel is cheaper than text. | LatCom and HyLaT report lower token/latency overhead in bounded settings; dense KV alignment reports large payloads and incomplete cost accounting. | **Conditional** | Measure bytes, transport, memory, adapter training/maintenance, wall-clock and energy. |
| A universal shared latent space is needed for the Holobiont. | Pair-specific adapters can provide interoperability without forcing all organs into one global geometry. | **Not established; unnecessary as a design assumption** | Compare private local spaces plus pairwise adapters against global shared-space training. |

## Source classification
- **Peer-reviewed:** LatCom (EMNLP 2026); HyLaT (EMNLP 2026).
- **Preprints:** Zhang & Emu causal audit; Cheng et al. causal audit; Chen et al. dense heterogeneous KV alignment; Piepereit architecture-dependent activation transfer; Brito & Baquero KV integrity; Liu BOUNDARY_SYNC.
- **Survey/preprint:** Beyond Tokens framework survey.

## Required evidence standard
A latent-communication claim must include: (1) receiver-necessity calibration, (2) true-versus-deranged payload intervention, (3) no-message and malformed/random controls, (4) compute-matched receiver self-generation, (5) independent task verification, and (6) total resource and security accounting.
