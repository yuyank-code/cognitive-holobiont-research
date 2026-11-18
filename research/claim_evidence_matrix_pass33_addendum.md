# Claim–Evidence Matrix Addendum — Pass 33 (2026-11-18)

| Claim | New evidence | Boundary / counterevidence | Status |
|---|---|---|---|
| A known damaged layer can be localized and repaired | SHNN (Scientific Reports, 2026) uses activation discrepancy and local patch layers; NSRepair (CAAI Transactions, 2026) uses Shapley localization and multi-objective repair | SHNN depends on clean pre-damage activations and has weaker CNN recovery; NSRepair reports >100M parameter cost limits and one defect objective per run | Supported in bounded settings |
| Hypernetworks can recover forgotten behavior | HyperRepair (Oct 2026 preprint) generates small repair side-nets for LoRA-adapted Qwen2.5-7B and Llama-3.1-8B; reports 93.4% base general score and 99.5% domain retention on default split | Existing backbone and adapted model remain; separate HyperNets per backbone; no missing-organ regeneration; preprint | Promising, narrow |
| One generator can instantiate heterogeneous model families | UHN (Apr 2026 preprint) reports vision, graph, text and formula tasks, multi-model, multi-task and recursive generation | Small-scale tasks, single RTX 4090; direct-training gaps; no non-trainable state; recursive accuracy declines; no deleted-specialist recovery | Promising, early |
| A missing independent specialist can be regenerated from surviving organs alone | No new source in this pass demonstrates this exact setting | New repair papers retain clean teacher activations, existing base models, task data or shared generators; unique information may be lost | Unvalidated |
| Byzantine influence can be contained in decentralized LLM networks | SAC (EMNLP 2026) uses receiver-side scoring, filtering and (F+1)-robust graph conditions | n=7/9, single-turn, static graph, bounded F-local threat model, objectively verifiable tasks; evaluator can be wrong; communication cost rises | Supported conditionally |
| Self-reported confidence is a safe trust signal | CP-WBFT (AAAI 2026) studies confidence-probe weighting | SAC identifies falsified sender confidence as a vulnerability; confidence probe results are task/topology dependent | Not a safe default |
| Closed-loop topology improves resilience | MAS-FIRE preprint reports >40% of catastrophic faults in linear workflows neutralized by iterative closed-loop designs | Three representative architectures and injected fault taxonomy; preprint; replication and matched-cost study needed | Promising |
| A capability-improving mutation is automatically safe to retain | EvoUndo finds many positive mutations fail recovery verification | Recovery depends on state-address grounding and recovery-language expressivity; exact snapshots outperform when pre-state is known | Rejected |
| Persistent self-modification should be gated by recoverability | EvoUndo supports recovery verification and counterfactual testing; snapshots/WAL remain preferable when available | Needs replication in multi-organ systems and against adaptive attackers | Strong design recommendation |
| Holobiont-specific regeneration beats best backup/retrain baseline | No matched-budget experiment yet | All relevant new evidence is narrower than the Holobiont claim | Unvalidated |

## Status vocabulary
- **Supported in bounded settings:** direct empirical evidence exists, but only within the stated scope.
- **Promising, narrow/early:** evidence exists but is preprint, small-scale, or limited to a related task.
- **Unvalidated:** no direct decisive experiment.
- **Rejected:** a broad assumption is contradicted by evidence or lacks a valid basis.
