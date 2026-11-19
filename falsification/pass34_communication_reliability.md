# Falsification Framework — Pass 34: Communication and Evidence Resilience

## Distinctive claims under test

### Claim A — The connective tissue makes organs more resilient
Falsified or narrowed if added communication paths do not preserve valid evidence under injected faults, or if the benefit disappears when compared with a simpler independent-source reacquisition baseline.

### Claim B — Continuous latent sharing improves cognition
Weakened if selective structured/hybrid sharing matches or exceeds latent communication at equal information, compute, bandwidth, latency and verification budgets. Also weakened if latent transfer cannot preserve provenance, uncertainty and temporal validity.

### Claim C — More connected topology is safer
Falsified if additional edges merely replicate the same upstream evidence, increase correlated propagation, or make fault detection harder. Route redundancy must be reported separately from source/evidence independence.

### Claim D — The system can self-heal communication failures
Weakened if unguided retries perform as well as trace-anchored diagnosis and intervention, or if recovery cannot reproduce the original failure deterministically enough to establish causality.

## Required adversarial controls

- Partial but syntactically valid messages.
- Stale evidence and expired context.
- Corrupted content that remains plausible.
- Invalid or semantically altered tool arguments.
- Shared source corruption before branching.
- Multiple branches carrying one common corrupted source.
- Receiver/verifier compromise.
- Poisoned shared memory or codec.
- Correct minority evidence that conflicts with the majority.
- Network churn and concurrent state updates.

## Required reporting

Every result must report:
- task success on clean and faulted executions;
- silent failures and detection latency;
- evidence provenance and completeness;
- independent source count and failure-domain ancestry;
- recovery and false-recovery rates;
- token, compute, memory, bandwidth, latency and verifier cost;
- task-clustered uncertainty intervals and repetitions.

## Stop conditions

Do not call the architecture fault-tolerant if:
- only transport failures are detected while semantic omissions remain silent;
- redundant paths share the same source and are described as independent evidence;
- a system declares recovery without passing held-out contracts;
- routing gains disappear under matched resource budgets;
- latent bridges are credited for gains caused by extra information, duplicated compute or stronger verification.
