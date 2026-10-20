# Claim–Evidence Matrix Addendum — Pass 31
Date: 2026-10-21

| Claim | Evidence reviewed | Current status | Main caveat / decisive next test |
|---|---|---|---|
| Persistent memory governance improves long-horizon task performance | MemGuard reports gains over ReasoningBank and verifier-only controls across 4 benchmarks, 4 backbones, 5 seeds | Promising, preprint-supported | Verifier labels are noisy; test independent replications and systematic/adversarial verifier error |
| Memory failure is only due to insufficient capacity | Supersede reports that proportional memory expansion did not recover a longer-history accuracy drop in n=25 | Contradicted in the tested setup | One preprint, bounded setting; test larger histories and independent runs |
| Temporal update policy is trainable | Supersede reports 9.0% to 16.7% held-out supersession accuracy after one GRPO run | Preliminary proof of mechanism | Absolute performance remains low; replicate across seeds, models, and update types |
| Provenance guarantees correct memory | Agent Zero Memory and Eywa use source pointers/citation discipline | Partially supported for grounding, not correctness | Provenance does not guarantee source truth, currentness, authorization, or correct interpretation |
| A unified memory score captures system readiness | LongMemEval, MemGuard, Supersede, and memory architectures measure different constructs | Rejected as an evaluation simplification | Report temporal currency, evidence quality, governance, retrieval, and utility separately |
| Adaptive communication guarantees correct collective decisions | Consilience reports round-wise calibrated one-step surrogate-regret bounds | Narrowly supported for its stated guarantee | No global trajectory or final-correctness guarantee; validate surrogate against end-task utility |
| More agents and more communication solve information silos | Peer-reviewed SILO-BENCH finds a communication-reasoning gap and collapse on hardest large-team tasks | Contradicted as a general claim | Positive task-specific cooperation remains possible; compare matched baselines and task regimes |
| Combined memory governance and adaptive communication create Holobiont-specific synergy | No evaluated source tests the complete proposed combination against strong matched alternatives | Unvalidated hypothesis | Factorial ablation with ownership swaps, held-out temporal updates, risk constraints, and total-cost accounting |

Evidence class notes:
- Peer-reviewed benchmark evidence: LongMemEval (ICLR 2025), SILO-BENCH (ACL 2026).
- Preprint evidence: MemGuard, Supersede, Agent Zero Memory, Eywa, MemPO, Consilience.
- Self-reported benchmark gains are not independent replications. Headline scores across different splits, judges, backbones, and budgets must not be compared as a unified leaderboard.
