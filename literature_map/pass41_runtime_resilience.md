# Living Literature Map — Pass 41: Runtime Resilience

## Theme map

| Research theme | New representative source | What it contributes | Remaining gap for the Holobiont |
|---|---|---|---|
| Controlled fault injection | AES, IEEE eScience 2026 | Repeatable format/logic/tool-call faults at chosen role and step | Broader semantic tasks and independent recovery methods |
| Fault diagnosis | AgentChaosBench, arXiv:2608.14680 | Labeled traces, fault type and location diagnosis | Current zero-shot detectors weak; more baselines needed |
| Online containment | Airlock, arXiv:2611.06727 | Provenance DAG, authority boundaries, selective cut | Supplied origin alert, trusted runtime, limited coordinator scale |
| Streaming monitoring | ResonAct, arXiv:2609.34701 | Runtime metrics and policy-based remediation | False-positive and recovery-rate trade-offs |
| Silent semantic fault detection | Loud Failures/Quiet Failures, arXiv:2610.10062 | Separates noticing, replanning, recovery and repetition | Broader tasks and independent verification |
| System reliability modeling | More Agents, More Reliable?, arXiv:2611.07140 | Operational profile, common-cause and combiner reliability envelopes | More tasks, more fault profiles and replicated controls |
| Readout versus representation loss | Three-interface continual-learning diagnosis, arXiv:2611.30151 | Separates deployed head failure from recoverable representation | Transfer to generative specialist organs and live repair |

## Synthesis

The field is developing the individual components of runtime resilience faster than it is demonstrating a complete closed-loop system. Fault injection, telemetry, provenance-guided containment and local repair each have bounded evidence. Their integration across long-running heterogeneous specialist networks remains unproven.

A key architectural split emerges:
- **Safety enforcement** should be deterministic and local at action boundaries.
- **Fault diagnosis** can use statistical and model-assisted inference, but must expose uncertainty and false positives.
- **Recovery planning** may be model-assisted, but must be independently verified.
- **Memory repair** must trace all descendants of a tainted artifact.
- **Reintegration** requires capability, state, permission and provenance checks.

## Citation trail / follow-up
- Follow AES to controlled fault injection and classic distributed-system chaos testing.
- Follow AgentChaosBench to trace attribution and paired counterfactual execution.
- Follow Airlock to information-flow control, capability attenuation, provenance DAGs, transaction fencing and distributed control-plane availability.
- Follow ResonAct to streaming observability, runtime verification and anomaly detection.
- Follow Loud Failures/Quiet Failures to silent data corruption and fault-tolerant tool use.
- Follow the three-interface continual-learning paper to disentangle readout mismatch from representation damage before labeling a specialist as lost.
