# Claim–Evidence Matrix Addendum — Pass 23 (2026-10-12)

| Claim | New evidence | Status after Pass 23 |
|---|---|---|
| Communication volume alone enables distributed computation | SILO-BENCH: active communication can coexist with failed synthesis as complexity grows | Contradicted in naive form |
| Multi-agent coordination must be evaluated over long horizons | AgentWorld: 25–55 rounds expose plan decay, role confusion, and wasted actions | Supported in tested sandbox; external generality open |
| Active elicitation is always desirable | SOTOPIA-TOM adds recipient/channel-dependent disclosure policy and privacy violations | False without authorization constraints |
| Shared memory needs explicit governance | Governed Shared Memory identifies leakage, stale propagation, contradiction persistence, lineage collapse and implementation-ordering bugs | Strong systems hypothesis; broad task gains not established |
| Perfect memory consolidation removes source bias | Memory Contagion reports bias propagation under oracle consolidation | Contradicted in tested settings; some bias-specific results preliminary |
| Transcript review is enough to audit cooperation | Colosseum separates text plans from realized action-level outcomes | Contradicted as a general assumption |
| A graph attribution metric establishes causal contribution | AgentWorld's CCE is useful diagnostically, but graph edges require intervention validation | Unsupported without interventions |
| More agents or denser communication monotonically improve quality | SILO-BENCH and AgentWorld report scale/coordination failures; equal-token studies are a negative control | Contradicted in general form |
| Evidence stewardship improves safety and utility jointly | Convergent design motivation across information-management, memory-governance, and audit work | Plausible systems hypothesis; causal benefit open |
| Holobiont-specific synergy exceeds best feasible alternatives | No intervention-validated, resource-matched cross-domain result yet | Unvalidated |

## Required revision to evaluation practice

Separate:
1. coordination success,
2. permitted information acquisition/disclosure,
3. memory integrity over time,
4. action-level cooperative utility,
5. causal contribution validated by intervention,
6. total resource cost.

Do not hide failures in one dimension inside a composite score.
