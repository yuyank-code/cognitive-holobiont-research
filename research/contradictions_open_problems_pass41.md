# Contradictions, Negative Results and Open Problems — Pass 41

## Contradictions and negative results

1. **More workers do not protect a bad aggregator.** AES finds aggregator-level logic injection catastrophic across all tested models; context/annotation growth also degrades aggregation. Worker redundancy is irrelevant if the reducer corrupts the final result.
2. **Error annotations do not automatically change behavior.** In AES, immediate, delayed and silent detection conditions produced the same final numerical output in the tested workflow.
3. **Silent semantic faults are harder than explicit exceptions.** Loud Failures/Quiet Failures reports detection in 91.3% of explicit-error trials versus 58.8% for plausible wrong values; a simple “check each result” instruction did not help.
4. **Runtime monitors can over-intervene.** ResonAct's AppWorld/Granite configuration reached 100% recall but a 72.97% false-positive rate.
5. **Diagnosis is weaker than containment.** AgentChaosBench's zero-shot detectors perform poorly on fault type and location; guardrail bypass is particularly difficult from a single trace.
6. **Selective containment depends on the alert and trusted runtime.** Airlock's strongest safety result assumes an initial fault-origin set and complete mediation by a trusted computing base. Symptom-only origin ranking remains uncertain.
7. **Centralized control introduces a new bottleneck.** Airlock reports coordinator journal saturation beyond roughly ten agents across three hosts; a central Heart can become a common failure point.
8. **A successful retry is not proof of repair.** Run-to-run stochasticity makes counterfactual comparison essential; recovery must be evaluated against matched clean runs and verified final state.
9. **Output regression is not always capability deletion.** A newly trained readout can recover much of the performance lost through head/backbone mismatch in continual-learning experiments.

## Open problems

- How can a detector distinguish a plausible but wrong result from a correct unusual result without an oracle?
- How should a system combine deterministic invariants, statistical anomaly detection and model-based semantic critique?
- Can provenance be complete across tools, hidden state, latent messages, summaries, caches and external effects?
- What happens when the provenance journal is delayed, forked, corrupted or unavailable?
- Can local enforcement remain safe during coordinator failure or network partition?
- How can root cause be localized when the only alert is a downstream symptom and multiple ancestors are plausible?
- How should a system decide between local retry, changed-plan retry, recomputation, rollback, substitution and quarantine?
- What counts as recovery when memory descendants and pending actions have already consumed a faulty output?
- How can a repaired organ be prevented from reintroducing stale or poisoned state?
- What is the operational cost of false quarantine in long-running workflows?
- Can reliability claims be made under uncertain deployment task/fault distributions?
- How should model readout, adapter, representation and capability degradation be diagnosed separately?

## Required caveats

- AES is a controlled numerical integration workflow, not a general cognitive-agent benchmark; its abstract/table state 194 jobs while one body passage says 198, and 184 results completed after 10 job failures.
- Airlock's zero post-alert leak result is conditional on its threat model, supplied origin alerts, trusted runtime and fenced convergence; it does not prove general fault discovery or agent-memory rollback.
- ResonAct's task completion gains must not be conflated with its lower recovery fraction among detected failures.
- AgentChaosBench's first baselines are zero-shot LLMs; rule-based and specialized detectors are not yet evaluated.
- All reported rates are benchmark- and denominator-specific.
