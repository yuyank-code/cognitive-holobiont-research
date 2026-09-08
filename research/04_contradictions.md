# Contradictions and Adversarial Evidence

This is a first-class research artifact. Evidence that weakens, contradicts, or places limits on a Holobiont claim must be preserved rather than filtered out.

## Run 20 additions

### C-039 Causal latent-transfer effects are real but not universal
- **Claim:** Latent relay gains generally demonstrate novel sender-specific information transfer.
- **Claim IDs:** CH-003
- **Evidence challenging it:** Two 2026 causal audits find cells where message presence or other-example content explains substantial gains, and effects vary across model scale/task.
- **Evidence supporting:** Both audits find sender/example-specific effects when the receiver genuinely needs sender-private information.
- **Current interpretation:** Novel latent information transfer is now supported conditionally, not universally. The correct question is when the channel reduces receiver uncertainty about information unavailable elsewhere.

### C-040 Communication can fail at the integration stage even when information is acquired
- **Claim:** Giving specialists access to distributed information is sufficient for distributed cognition.
- **Claim IDs:** CH-006/CH-025
- **Evidence challenging it:** SILO-BENCH finds active communication and acquisition of relevant information followed by failure to synthesize distributed state; hardest tasks collapse at scale.
- **Evidence supporting:** Some adaptive topologies and task-structured communication improve efficiency/performance.
- **Current interpretation:** A Holobiont needs an explicit integration mechanism; communication bandwidth alone is insufficient.

### C-041 Uncertainty is path/topology dependent
- **Claim:** Specialist confidence/final-output uncertainty can be aggregated independently.
- **Claim IDs:** CH-009/CH-023
- **Evidence challenging it:** MATU identifies cascading uncertainty, communication-path variability, and topology diversity as distinct sources of reliability variation.
- **Current interpretation:** Fusion should weight dependency structure and execution trajectory, not just marginal confidence.

### C-042 Training-free alignment does not establish universal interoperability
- **Claim:** A portable latent bridge can connect arbitrary specialists.
- **Claim IDs:** CH-002/CH-024
- **Evidence challenging it:** StateBridge is promising but tested on limited model families/tasks; model-stitching work shows stitch training objective and depth strongly affect success.
- **Current interpretation:** Interface compatibility is empirical and should be tested pairwise/regionally, not assumed globally.

### C-043 Byzantine filtering can improve reliability without establishing truth
- **Claim:** Byzantine-resilient consensus is a truth mechanism.
- **Claim IDs:** CH-010/CH-026
- **Evidence challenging it:** SAC improves suppression of malicious influence, but robust agreement only protects against modeled adversarial behavior; correlated truthful-but-wrong evidence and specification errors remain distinct.
- **Current interpretation:** Byzantine robustness is a fault-containment property, not an epistemic guarantee.

## Prior contradictions retained

### C-034 MoE routing stability is not the same as durable cognitive specialization
Induced specialization can be overwritten by subsequent multimodal training.

### C-035 Large latent-channel effects can occur without sender/example-specific transfer
A relay effect can survive mismatched examples; large accuracy gains do not identify the information source.

### C-036 Communication density can coexist with zero distributed computation
SILO-BENCH demonstrates active communication without successful distributed integration.

### C-037 Hypernetwork scaling does not close capability regeneration
Adapter generation is not recovery of unique destroyed capability.

### C-038 Consensus can be useful without being the epistemic objective
Consensus is a coordination primitive, not a truth criterion.

### C-027 through C-033
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
