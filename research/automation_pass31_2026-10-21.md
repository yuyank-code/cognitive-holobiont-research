# Cognitive Holobiont Research — Pass 31
Date: 2026-10-21

The Treatise/PDF remains a hypothesis, not established fact. Implementation is deferred.

## Findings
**MemGuard (preprint, arXiv:2608.21867):** across four interactive benchmarks, four backbones, and five seeds, persistent verifier metadata plus lifecycle governance reportedly beats a verifier-only filter and ReasoningBank. Removing governance caused the largest ablation loss. But verifier labels matched author inspection in only 83–86% of an 800-decision audit; a separate outcome check reported 88.1% macro balanced accuracy and 9.3% false positives. Persistent metadata can reduce error propagation, not make a fallible verifier authoritative.

**Supersede (preprint, arXiv:2606.27472):** the authors report 92% versus 77% for full context versus bounded memory on a tested update subset. In a longer-history test, accuracy fell 68% to 28%; proportional memory expansion did not recover it in n=25. One GRPO run raised held-out supersession accuracy from 9.0% to 16.7%, still low in absolute terms. This supports an update-policy bottleneck in that setup, not a universal claim about memory capacity.

LongMemEval (ICLR 2025, arXiv:2410.10813) separates temporal updates from extraction, retrieval, multi-session reasoning, and abstention. Agent Zero Memory (arXiv:2608.29606) emphasizes event timelines and citation-locked evidence; Eywa (arXiv:2605.30771) preserves source evidence before derived facts; MemPO (arXiv:2603.00680) learns task-aware compression. Their headline scores are not a common leaderboard because splits, judges, backbones, budgets, and metrics differ.

Consilience (preprint, arXiv:2608.20564) reports benefits from adaptive communication, but its guarantee is round-wise one-step regret under a surrogate loss, not final correctness. Peer-reviewed SILO-BENCH (ACL 2026) finds that active communication does not ensure effective distributed computation.

## Revised hypothesis
Maintain an evidence ledger (source, time, scope, authorization, lineage, supersession relation) separately from a belief/decision ledger (derived claim, verifier state, uncertainty, validity, receiving agents, dependent plans). Keep historical evidence auditable while revoking derived beliefs and reevaluating queued actions after updates. Count communication gain only after freshness, support, scope, and authorization checks.

## Falsification
Compare retrieval-only, learned compression, verifier-only admission, lifecycle governance, and temporal versioning, with adaptive routing on/off. Match history, memory, model, tool, verifier, and cost budgets where possible. Measure stale-answer/action rates, invalidation lag, false admission/retirement, provenance coverage, verifier calibration, final utility, privacy failures, benign false rejection, and total cost. Weaken the claim if governance fails against simpler controls, versioning fails to reduce stale actions, or routing gains vanish after full cost and authorization controls. Holobiont-specific synergy remains unvalidated.
