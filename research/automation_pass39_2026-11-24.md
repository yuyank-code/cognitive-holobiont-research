# Cognitive Holobiont Research — Pass 39
**Date:** 2026-11-24  
**Focus:** Causal utility, cross-model interoperability, efficiency, and security of the Connective Tissue / latent communication layer.

## Executive conclusion

The originating Treatise proposes learned bridges between specialist latent spaces so organs can exchange more than compressed natural-language summaries. This pass asks a stricter question:

**When a receiver consumes a sender's hidden representation, does it use the example-specific information that sender actually observed, and does that information improve the receiver beyond a compute-matched self-generated alternative?**

The evidence supports a conditional answer:

- **Latent transfer is technically real in bounded settings.** Native KV relay can transmit sender-private, example-specific information when the receiver genuinely lacks it.
- **A benchmark gain is not proof of content transfer.** In ordinary tasks where the receiver can solve the problem itself, a cache may help through generic interface/computation effects even when swapping in a different example's cache barely changes performance.
- **Cross-model transfer is possible but pair-, architecture-, context- and task-dependent.** Some learned adapters work across selected model families; other activation-transfer tests fail at the generation level despite representational alignment.
- **Hybrid latent-plus-text communication is the most defensible near-term design candidate.** It can preserve compact machine-to-machine signals while retaining readable commitments and interoperability, but current results are small-model and limited-topology studies.
- **Latent state is a security-sensitive payload.** A text verifier cannot establish that a hidden cache is benign or consistent with the visible commitment. Transport authentication can detect post-handoff tampering, but cannot make a malicious endpoint truthful.

The Treatise's connective-tissue hypothesis is therefore upgraded from speculative to **conditionally feasible as an engineering channel**, not to a universal shared cognitive language or proof of shared meaning.

## 1. Project-specific question

The Holobiont is not a collection of generic chat agents. Its organs are intended to remain heterogeneous, retain private expertise and exchange task-relevant state through learned bridges, a compact shared bloodstream and a temporal narrative mechanism.

The crucial design tension is that a richer latent channel may preserve information lost by text, but it can also:
- bind the system to specific model checkpoints, layers, tokenizers or pair-specific adapters;
- increase memory and network payload size;
- transmit stale, misleading or malicious internal state that cannot be inspected as prose;
- cause a receiver to change its output without using the sender's example-specific evidence;
- homogenize responses when shared context causes premature convergence;
- make provenance, privacy and incident investigation harder.

The research target is therefore not maximum latent bandwidth. It is **auditable transfer of useful, receiver-needed information at a lower total cost and acceptable risk**.

## 2. New evidence

### 2.1 Causal audits: message presence is not message content

Zhang and Emu's July 2026 preprint, *Do Latent Channels Actually Communicate?*, introduces a common intervention at the sender-to-receiver message boundary. It compares no message, a current-example message, an other-example message and a receiver-generated self-message. Its measurements distinguish encoded sender information, receiver sensitivity, example-specific task value and the additional value of a separate sender.

On GSM8K with Qwen3-4B, the overall latent-message effect is -1.00 percentage point, but it decomposes into a -6.17-point other-example-message effect and a +5.17-point example-specific-content effect. On MATH-500 with Qwen3-4B, the +15-point overall effect decomposes into +8.33 points from the other-example message and +6.67 from example-specific content. The decomposition changes with model size and task. On GSM8K, Qwen3-4B's +5.17-point content-attributable gain does not establish unique sender value: its self-substitution gap is -2 points with an interval crossing zero. On MATH-500, the Qwen3-8B sender's self-substitution comparison does show a positive 10-point separate-agent contribution, while its example-specific-content estimate is only +1.88 points with an interval crossing zero.

The implication is methodological: a receiver can be sensitive to a latent payload without using the payload's current-example content, and current-example content can help without proving that a separate sender adds value beyond the receiver's own matched computation. This is a preprint with six model/task configurations, modest sample sizes and no broad heterogeneous specialist population.

Source: [Zhang & Emu, arXiv:2607.26773](https://arxiv.org/abs/2607.26773).

### 2.2 Receiver necessity determines whether the channel's content matters

Cheng, Das and Ramnath's August 2026 preprint, *When Does Latent Communication Pay?*, audits released KV-relay systems using true, deranged (mismatched-example), zeroed and moment-matched random caches. It separates a calibrated regime, where the receiver lacks sender-private facts, from natural benchmarks where the receiver can solve the task itself.

In the calibrated regime, native LatentMAS relay reaches approximately 100% while answer-irrelevant relays achieve roughly 23–25% on the primary Qwen3-8B cell; the effect is replicated across Qwen3-4B/8B/14B, Mistral-Nemo-12B and Phi-4, plus a prose document-QA construction. This is strong evidence that a native KV channel can carry and deliver example-specific private information when the receiver needs it.

In the natural regime, a five-seed, preregistered equivalence analysis bounds the true-versus-deranged pairing effect within ±2.8 percentage points for the specified Qwen3 cells. One MedQA example shows a 14.7-point true-versus-zero cache effect but only a 0.4-point true-versus-deranged effect. That means the cache's presence can matter while its example-specific pairing contributes little. The audit also finds different transfer behavior across delivered channels: native relay shows strong content transfer, KVComm partial transfer, and the tested released C2C projector no detected example-specific transfer under its calibrated audit.

This is a preprint, not a peer-reviewed replication. Its natural benchmark items include receiver-redundant information and some are training-split items; its equivalence margin is anchored to the audited system's own reported aggregate gain. Those choices are disclosed and should be preserved when interpreting the result.

Source: [Cheng et al., arXiv:2608.04893](https://arxiv.org/abs/2608.04893).

### 2.3 Heterogeneous KV-cache alignment: promising, but expensive and pair-specific

Chen et al.'s October 2026 revised preprint, *See What I See, Know What I Think*, aligns sender KV caches to a receiver's cache space using positional disentanglement, layer alignment, per-KV-group transformations and gates. It distinguishes:
- context-aware transfer, where the receiver already sees the sender's source input;
- context-unaware transfer, where the receiver relies on the cache for that source information;
- partial-awareness, where agents hold complementary private documents.

Across six directed Qwen3 size pairs, the method reports better in-domain accuracy than text-to-text transfer on the tested tasks, with fewer estimated model FLOPs. A Mistral-7B-to-Qwen3-4B pair also improves on the three in-domain tasks but trails text on three held-out tasks. In a three-agent HotpotQA setting, two senders encode separate documents and a different receiver combines their caches; the reported latent method beats both full-document text transfer and a receiver-only raw-document baseline in the three tested configurations.

Important limits:
- each new model pair requires training a new adapter;
- the experiments reach only three agents and a small number of cross-family configurations;
- dense caches use approximately 27–30 MB per example in the reported accounting, versus roughly 3–4 kB for generated text;
- the FLOPs estimate omits adapter training, transport, serialization and cache-processing costs, and is not a measured end-to-end deployment-cost comparison;
- some cross-family held-out task results regress relative to text.

This is relevant evidence for a learned bridge, not evidence of a universal shared latent space.

Source: [Chen et al., arXiv:2606.13594v2](https://arxiv.org/abs/2606.13594).

### 2.4 Latent compression: reduce cross-organ redundancy before it reaches the receiver

LatCom is a peer-reviewed EMNLP 2026 paper. It jointly compresses multiple sender trajectories into a fixed number of receiver-readable latent slots, training a single-sender interface and then a multi-sender fusion compressor. On Qwen3-4B/8B, it reports comparable average accuracy to full relay, a 2.46× average inference speed-up over LatentMAS and 70.3% lower output-token use. Its detailed comparison reports roughly 1.9 and 1.77 percentage-point average improvements over independently compressed-and-concatenated Interlat on Qwen3-4B and Qwen3-8B, respectively.

The limitation is central to the Holobiont: LatCom relies on aligned representations within the same model family, uses a fixed 64-slot budget in the reported three-sender setup, and acknowledges that full relay is stronger on some code-generation tasks. It is an efficiency/compression result, not a demonstration of cross-family organ interoperability.

Source: [Zhang et al., EMNLP 2026](https://aclanthology.org/2026.emnlp-main.1068/).

### 2.5 Hybrid latent-text channels: a practical bridge between efficiency and auditability

HyLaT is a peer-reviewed EMNLP 2026 paper. It sends elaborate intermediate signals through latent tokens and concise critical commitments through text. It supports multi-round interaction after two-stage training. A small heterogeneous variant pairs Llama-3.2-1B and Qwen2-1.5B with per-agent adapters in a two-agent, two-round task.

Its limits are material: experiments use 1B/3B models, its modified generation procedure is not compatible with vLLM in the reported implementation, the latent channel remains opaque, and its text communication training data are mainly QA/debate-style. Scaling agent count and rounds does not consistently improve accuracy.

The design principle is useful: **use latent payloads for compact machine-to-machine intermediate state, but keep decisions, commitments, provenance and failure signals in an inspectable channel.**

Source: [Mou et al., EMNLP 2026](https://aclanthology.org/2026.emnlp-main.181/).

### 2.6 Representational alignment does not guarantee causal transfer

A separate August 2026 preprint tests projected activations between Qwen2-0.5B, Phi-3-mini, Mistral-7B and FLAN-T5. Learned projections retrieve target representations above chance for three decoder-only pairs, but end-to-end activation injection produces a significant retrieval-neighbourhood effect for only one of the three tested decoder-only pairs (Qwen2-0.5B to Phi-3-mini: 23.3% versus 0% under negative control; FDR-corrected p=0.047). Two pairs targeting Mistral show no such effect despite similar representational alignment. The authors explicitly do not claim semantic understanding or a general-purpose communication channel.

This strengthens the distinction between representation similarity, decodability, receiver sensitivity and task-relevant causal use.

Source: [Piepereit, arXiv:2608.16347](https://arxiv.org/abs/2608.16347).

### 2.7 Communication can homogenize agents

BOUNDARY_SYNC, a July 2026 preprint, reports communication-induced output homogenization in controlled GPT-4o text and image experiments. It also reports large cross-model variation. Its limitations include a self-anchoring confound, group-size/prompt-length confounding and a single stereotype-assessment task domain. It should motivate a diversity-retention measurement, not be treated as a universal group-size rule.

Source: [Liu, arXiv:2607.01600](https://arxiv.org/abs/2607.01600).

### 2.8 Hidden-state integrity is a separate security boundary

Brito and Baquero's June 2026 preprint, *When Latent Agents Lie*, shows that a plausible visible commitment can accompany a malicious or corrupted KV payload. Text-only verification misses hidden-state manipulation; simple magnitude checks can be evaded by adaptive attacks. Their HMAC-SHA256 manifest accepts 774/774 honest replayed payloads and rejects 295/295 recorded tampered payloads.

This result must be scoped correctly: HMAC can authenticate a payload after handoff if the key and transport boundary are trusted. It does not prove that a compromised endpoint produced a truthful or safe payload before signing it. The paper explicitly leaves endpoint compromise, key management, remote attestation, broad semantic validation and privacy measurement open.

Source: [Brito & Baquero, arXiv:2606.28958](https://arxiv.org/abs/2606.28958).

## 3. Revised connective-tissue architecture

The strongest current candidate is an **auditable hybrid communication fabric**, not an always-on universal latent bloodstream.

Each organ-to-organ edge should declare:
- sender and receiver model/checkpoint/adapter versions;
- task and episode identifiers;
- source evidence identifiers and provenance;
- whether the receiver already has the source input;
- payload type (text, typed structure, embedding, hidden state or KV cache);
- codec/adapter version and tensor metadata;
- freshness, scope, uncertainty and authorization;
- integrity digest/authentication metadata;
- a visible concise commitment or decision record.

Communication policy:
1. Keep private specialist representations local by default.
2. Use typed structured evidence for provenance, permissions, commitments and safety-critical decisions.
3. Invoke a latent bridge only when the receiver lacks relevant information or when a measured receiver-side benefit justifies it.
4. Prefer hybrid latent-plus-text where multi-round collaboration is required.
5. Compress multiple senders jointly when their latent trajectories are redundant, but retain a fallback to full relay for tasks that need fine-grained detail.
6. Verify transport integrity before injection; on integrity failure, fail closed and fall back to a validated text/evidence route.
7. Treat endpoint truthfulness as separate from transport integrity; a valid signature is not a truth certificate.
8. Measure whether communication preserves specialist diversity or causes premature convergence.

This preserves the Treatise's connective tissue and shared bloodstream ambitions while removing the unsupported assumption that every organ should continuously broadcast its entire internal state.

## 4. Mathematical formalization added

Let a receiver with fixed local context X receive one of four messages: no message M0, current-example message Mcur, other-example message Moth, or compute-matched receiver-generated message Mself.

Define:
- **Presence effect:** PL = D(Pcur, P0), measuring prediction sensitivity to message presence.
- **Content identity effect:** CIC = D(Pcur, Poth), measuring whether current versus mismatched content changes predictions.
- **Content-attributable utility:** CAG = U(Mcur) − U(Moth).
- **Separate-agent value:** SSG = U(Mcur) − U(Mself), where receiver-side self-generation is compute matched.
- **Pairing effect:** τpair = E[U | do(M=Mcur)] − E[U | do(M=Moth)].
- **Generic interface effect:** τgeneric = E[U | do(M=Moth)] − E[U | do(M=M0)].

In a private-information calibration, add an intact-format but answer-irrelevant message Mintact:
- **Private-content effect:** τprivate = E[U | do(M=Mcur)] − E[U | do(M=Mintact)].

These estimands are not interchangeable. A nonzero PL or CIC does not establish task value; a positive CAG does not establish that a separate sender is better than a compute-matched receiver; a positive true-versus-zero cache effect does not establish correct example-specific transfer.

For multi-sender coalitions S, evaluate the conditional marginal contribution of organ i:
Δi(S) = U(S ∪ {i}) − U(S),
and coalition interaction:
Iij(S) = U(S ∪ {i,j}) − U(S ∪ {i}) − U(S ∪ {j}) + U(S).

All utilities must be measured with external or otherwise independent verification and reported alongside total cost.

## 5. Decisive experiment programme

The next experiment is not to build a universal latent bus. It is a controlled audit across three communication regimes and multiple channel implementations.

**Regimes**
A. Receiver already sees sender input.  
B. Receiver lacks sender-private evidence.  
C. Receiver has partial overlapping context and must combine multiple private observations.

**Channel arms**
- no communication;
- text;
- typed structured evidence;
- native KV relay;
- learned cross-model KV/activation bridge;
- compressed multi-sender latent relay (LatCom-style);
- hybrid latent-text protocol (HyLaT-style);
- compute-matched receiver self-generation.

**Causal controls**
- current-example versus deranged/mismatched payload;
- intact-format but answer-irrelevant private evidence;
- zero and moment-matched random payloads;
- sender ablation and ownership swaps;
- receiver self-substitution;
- sender identity swap while preserving evidence;
- adapter trained on one family/task and evaluated on held-out pair/task.

**Security controls**
- post-handoff payload tampering and replay;
- stale session/model/codec metadata;
- signed malicious endpoint payloads;
- prompt injection embedded in sender-side evidence;
- shared codec/adapter compromise;
- payload integrity failure with text fallback;
- privacy reconstruction/leakage from transferred caches.

**Required measurements**
- accuracy/task utility and calibration;
- PL, CIC, CAG, SSG and τpair;
- total model FLOPs, training cost, bytes transmitted, peak memory, wall-clock latency and energy where available;
- adapter/codec maintenance cost across model versions;
- false rejection and undetected malicious payload rates;
- diversity/correlation before and after communication;
- robustness on held-out tasks and new model pairs.

Do not claim matched budgets using token counts alone. Dense KV payloads may be megabytes even when they avoid generated tokens. Report communication bytes and actual end-to-end latency, not only model FLOP estimates.

## 6. Falsification conditions

The distinctive latent-connective-tissue claim is weakened or falsified for a tested regime if:
1. true and deranged messages are practically equivalent when the receiver lacks sender-private information;
2. the sender's message does not outperform compute-matched self-generation;
3. observed gains persist with mismatched or answer-irrelevant payloads, indicating generic interface effects rather than content transfer;
4. a learned bridge fails on held-out model pairs or model updates at a cost that exceeds its utility;
5. typed text/structured evidence matches or beats latent communication on total cost, task quality and auditability;
6. hidden-state communication causes unacceptable security/privacy risk without a defensible validation and fallback path;
7. communication homogenizes specialist responses enough to erase the independent evidence the federation was intended to preserve.

A positive result must replicate across multiple model families, task regimes and independent seeds, and must survive the compute-matched self-substitution and mismatched-content controls.

## 7. Current conclusion

The Treatise's latent connective tissue is neither fantasy nor established universal technology. There is now peer-reviewed evidence for efficient latent compression and hybrid multi-round protocols, plus preprint evidence that native and learned KV interfaces can transfer private information across selected models and tasks. Equally important, causal audits show that many apparent latent-message gains may be generic cache/interface effects when the receiver already has the information, and security research demonstrates that hidden state is an opaque attack surface.

**The recommended near-term architecture is a selective, auditable, hybrid channel:** local private reasoning by default; structured provenance and commitments as the control plane; latent payloads only when the receiver demonstrably needs the information; learned pair-specific adapters with held-out validation; authenticated transport; and fail-closed text/evidence fallback.

The next milestone is a reproducible, multi-family private-evidence audit—not implementation of a continuous all-to-all latent bloodstream.

No evidence in this pass establishes shared semantic meaning between models, universal cross-architecture communication, Holobiont-wide collective cognition, AGI, consciousness, immortality or full regeneration.
