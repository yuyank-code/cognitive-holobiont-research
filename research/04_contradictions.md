# Contradictions and Adversarial Evidence

This is a first-class research artifact. Evidence that weakens, contradicts, or places limits on a Holobiont claim must be preserved rather than filtered out.

## Run 23 additions

### C-049 Latent communication can be useful while universal latent compatibility remains false
- **Claim:** A successful latent relay implies a shared semantic latent substrate.
- **Evidence challenging it:** Interlat relies on learned interfaces, supervised separation/plan alignment and bounded model/task families; its authors explicitly position the work as a feasibility study.
- **Evidence supporting:** Interlat reports cross-family communication, perturbation sensitivity and performance gains over text-based/single-agent baselines.
- **Current interpretation:** Treat latent communication as a learned protocol/interface. Do not assume arbitrary pairwise latent compatibility or a universal common latent space.

### C-050 Routing can fail before collective cognition begins
- **Claim:** Adding more specialists increases accessible collective capability.
- **Evidence challenging it:** LatentGate reports that embedding-based routers can collapse semantically similar but functionally distinct agents and lose OOD routing quality.
- **Evidence supporting:** Lightweight capability-aware probing with whitening substantially improves reported routing accuracy at low latency.
- **Current interpretation:** Capability-aware routing is part of the cognitive substrate; raw semantic similarity is insufficient.

### C-051 Diversity can be destroyed downstream by weak selection
- **Claim:** Diverse specialists naturally yield better collective answers.
- **Evidence challenging it:** Selection Bottleneck reports large differences between selection and synthesis and 53–67% attenuation under independent evaluation.
- **Evidence supporting:** Strong selectors can exploit heterogeneous candidate quality.
- **Current interpretation:** Generator diversity and integration competence are independent variables; selection must be independently evaluated.

### C-052 Communication can create problem drift
- **Claim:** More rounds of agent communication should improve collective reasoning.
- **Evidence challenging it:** Stay Focused documents measurable drift across ten tasks; the proposed mitigation fixes only a subset.
- **Evidence supporting:** Communication can improve bounded reasoning tasks when feedback is useful and anchored.
- **Current interpretation:** Persistent task anchoring, progress tests and termination/rollback are architectural requirements.

### C-053 Topology has no universally dominant coordination regime
- **Claim:** A single Holobiont topology should be optimal.
- **Evidence challenging it:** DESBench reports different trade-offs for centralized, hierarchical, heterarchical and holonic coordination.
- **Current interpretation:** The architecture should permit objective- and fault-dependent topology switching rather than hard-coding one organizational form.

## Prior contradictions retained

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
