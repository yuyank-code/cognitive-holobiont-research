# Contradictions and Adversarial Evidence

This is a first-class research artifact. Evidence that weakens, contradicts, or places limits on a Holobiont claim must be preserved rather than filtered out.

## Pass 09 additions — 2026-09-17

### C-054 Latent payload requirements depend on receiver context
- **Claim challenged:** A fixed latent representation/compression ratio is an intrinsic measure of communication quality.
- **Evidence:** June 2026 heterogeneous latent-communication work distinguishes context-aware transfer, where the receiver already has the input, from context-unaware transfer, where contextual knowledge itself must be transmitted. The information structure and useful payload density differ between regimes.
- **Interpretation:** Communication utility must be conditioned on receiver-private information. Compression numbers are not portable across protocols without specifying what the receiver already knows.

### C-055 Heterogeneous latent transfer does not imply a universal latent language
- **Claim challenged:** If different models exchange hidden states successfully, they must share a common latent geometry.
- **Evidence:** Interlat and dense heterogeneous KV alignment use explicit learned transformations/interfaces. Successful cross-model transfer therefore demonstrates interoperability under an interface, not universal raw-state compatibility.
- **Interpretation:** The Holobiont should use typed/learned interfaces and treat representation alignment as an engineering layer. A single universal latent space is no longer a required hypothesis.

### C-056 Communication capacity can remain high while collective computation fails
- **Claim challenged:** Increasing latent bandwidth or communication density should close the distributed reasoning gap.
- **Evidence:** SILO-BENCH and MAS-BENCH show active communication with severe failure on tasks requiring global composition; scaling agent count can worsen performance.
- **Interpretation:** Information transport, information acquisition, and computation/integration must be evaluated separately.

### C-057 Repair is not resurrection
- **Claim challenged:** A self-healing network demonstrates recovery of a lost specialist capability.
- **Evidence:** SHNN restores damaged network behavior through local patching on small image datasets, but does not establish recovery of information absent from all surviving components.
- **Interpretation:** Functional repair and information-theoretic capability recovery remain separate claims.

## Prior contradictions retained

### C-049–C-053
Latent communication can be useful while universal compatibility remains false; routing can fail before collective cognition begins; diversity can be destroyed downstream by weak selection; communication can create problem drift; no single topology is universally dominant.

### C-044–C-048
Latent transfer is conditional; diversity can be wasted at selection; K* is not yet causal independence; communication does not automatically yield long-horizon distributed computation; MoE expert labels do not imply semantic organs.

### C-039–C-043
Causal latent-transfer effects are real but not universal; communication can fail at integration; uncertainty is path/topology dependent; training-free alignment does not establish universal interoperability; Byzantine filtering does not establish truth.

### C-034–C-038
MoE routing stability is not durable specialization; large latent-channel effects can occur without sender/example-specific transfer; communication density can coexist with zero distributed computation; hypernetwork scaling does not close capability regeneration; consensus can be useful without being the epistemic objective.

### C-027–C-033
Raw agent count is a poor proxy for capacity; diversity metrics can disagree; communication can homogenize or diversify; confidence is not automatically reliable; truthful fragments can form false collective beliefs; hypernetwork scaling is not regeneration; recursive memory evolution is not unrestricted core-model RSI.

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
13. Does specialist identity survive continued joint training?
14. Does a latent relay transfer sender/example-specific information under receiver isolation?
15. Can the system convert communication into exact distributed computation rather than conversational coordination?
16. Does topology-aware uncertainty predict failure better than output confidence alone?
17. Can training-free bridges generalize across model families without task-specific alignment?
18. Can Byzantine filtering remain reliable when honest agents share the same wrong evidence or specification?
19. Does selection quality explain most apparent diversity benefit?
20. Does long-horizon coordination retain gains after communication and memory budgets are matched?
21. Does capability-aware routing reduce collective regret rather than only improve route classification?
22. Can persistent task anchoring prevent communication-induced drift without suppressing useful exploration?
23. Can topology switching improve utility while preserving fault isolation and avoiding controller common-mode failure?
24. Does receiver context determine the minimum useful latent payload strongly enough to change optimal communication protocols?
25. Can a causal communication metric predict collective computation gains across model families rather than only within one interface family?
