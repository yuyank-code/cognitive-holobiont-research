# Claim–Evidence Matrix Addendum — Pass 29 (2026-10-19)

| Claim | Evidence added | Status |
|---|---|---|
| Agents infer what teammates know but have not said | Peer-reviewed HiddenBench reports failures under distributed information; structured elicitation helps in tested settings | Rejected as default assumption; elicitation remains open |
| Full-information single-agent comparison proves MAS inferiority | HiddenBench full-profile baseline has privileged information | Rejected; use as upper-bound diagnostic, not access-matched baseline |
| Aggregate success establishes safe long-horizon memory | MemRiskBench reports sharp per-risk differences hidden by aggregate scores | Rejected; require per-risk rates and hard limits |
| Deterministic scoring guarantees valid measurement | MemRiskBench audit changed 39/600 trace-episode scores | Rejected; scorer specifications need audits and mutation tests |
| Benchmark compression should preserve only model ranking | Risk-preserving selector separates ranking, risk coverage, high-risk detection | Rejected for safety-critical evaluation; external validity open |
| Stable call graph implies stable or correct behavior | MAESTRO reports temporal variability and silent semantic failures | Rejected |
| More complex/auto-generated MAS are generally better | Some auto-generated systems underperform at higher cost; expert design wins on decomposition-favorable synthetic task | Task/architecture interaction supported; universal complexity benefit rejected |
| Debate answer flips indicate peer learning | Counterfactual study separates self-instability, conformity, persuasion | Rejected; require controls and verified outcomes |
| One fixed scalar captures an agent's value independent of coalition | CoFi-PGMA preprint formalizes background-dependent contribution | Context-free attribution inadequate for interacting coalitions |
| Holobiont-specific synergy beats strongest feasible baselines | No complete resource-/information-/privacy-matched causal evidence | Unvalidated |

Keep separate: information acquisition, authorized transmission, integration, causal influence, verified utility, execution reliability, memory safety, total cost, and governance violations. Last reviewed: 2026-10-19.
