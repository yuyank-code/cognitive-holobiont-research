# Pass 31 Source Ledger
Reviewed 2026-10-21

- MemGuard, preprint: arXiv:2608.21867. Lifecycle governance, ablations, verifier audit, runtime overhead. Code: github.com/whyyyyy123/MemGuard.
- Supersede, preprint: arXiv:2606.27472. Temporal fact currency and update policy. Reported training gain is a single run; held-out accuracy remains low.
- LongMemEval, ICLR 2025: arXiv:2410.10813. Extraction, multi-session and temporal reasoning, updates, abstention. Code: github.com/xiaowu0162/LongMemEval.
- Agent Zero Memory, preprint: arXiv:2608.29606. Event timeline, entity-event graph, citation-locked memory.
- Eywa, preprint: arXiv:2605.30771. Immutable source evidence before derived facts.
- MemPO, preprint: arXiv:2603.00680. Learned task-aware memory compression.
- Consilience, preprint: arXiv:2608.20564. Adaptive communication with a round-wise one-step surrogate-regret guarantee.
- SILO-BENCH, peer-reviewed ACL 2026: ACL Anthology 2026.acl-long.1354. Negative evidence that active communication alone does not ensure distributed computation.

Citation-chain synthesis: LongMemEval separates updates from retrieval and reading; Supersede targets update policy; MemGuard isolates lifecycle governance against verifier-only filtering; provenance methods improve traceability but not currency; MemPO is a competing compression objective; Consilience needs current, authorized evidence signals. No independent replication of the newest MemGuard/Supersede results was identified in this pass; that is not proof none exists.