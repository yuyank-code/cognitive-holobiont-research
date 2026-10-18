# Contradictions and Open Problems — Pass 29 (2026-10-19)

## New contradictions
- **C-058 — Hidden knowledge vs information pooling:** distributed facts do not automatically become collective knowledge. Evaluate elicitation separately from broadcast.
- **C-059 — Oracle vs fair comparison:** a full-information single-agent baseline measures information-access headroom, not access-matched deployment performance.
- **C-060 — Aggregate score vs memory risk:** high overall success can coexist with weak cross-scope leakage performance; use risk vectors and hard constraints.
- **C-061 — Deterministic scorer vs valid specification:** trace checks can encode wrong expected values or refusal semantics; use mutation tests and independent review.
- **C-062 — Stable graph vs variable outcome:** structural similarity is not correctness or causal attribution.
- **C-063 — Consensus change vs peer-caused learning:** answer changes may occur without peer exposure; use self-reflection, stance-only, and rationale conditions.
- **C-064 — Individual score vs coalition-dependent contribution:** agent value may depend on the background coalition.
- **C-065 — Benchmark compression vs reference-set overfit:** a subset may preserve rankings on known models but miss new model families or rare risks.

## Open problems
1. Can an agent identify who may possess a decisive unexpressed fact without exposing private information?
2. What is the best access-matched baseline for complementary-private-information tasks?
3. How should benchmark subsets preserve rare risks under model/task shift?
4. Can trace-grounded risk checks achieve low false-positive and false-negative rates?
5. Which observability fields are minimally sufficient without retaining unnecessary private content?
6. Can protocol routing predict net marginal value on held-out tasks after charging routing and verification costs?
7. How should interaction effects be estimated when full coalition enumeration is infeasible?
8. Can independent outcome verification be maintained when verifiers share models, tools, or evidence?
9. Does a joint controller create common-mode failure through shared policy, memory, or routing?
10. Does Holobiont-specific synergy persist in state-changing long-horizon and risk-constrained deployments?

## Falsification conditions
Weaken or reject the synergy claim if gains vanish against access- and resource-matched baselines; disappear under ownership/identity swaps; depend on oracle information; increase consensus without verified utility; violate risk limits despite a higher mean score; vanish after router/retry/verification costs; rely on observational trace attribution; or fail held-out tasks and independent replications.
