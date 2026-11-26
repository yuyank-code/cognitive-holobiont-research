# Source Ledger — Pass 41 (2026-11-26)

## Peer-reviewed conference paper

### Bateman et al. — Agent Error Simulator: Fault Injection for Testing Recovery in Agentic Workflows
- Venue: 22nd IEEE International Conference on eScience, September 2026.
- DOI: https://doi.org/10.1109/eScience70237.2026.00052
- Institution page/PDF: https://grc.iit.edu/gnosis/publications/bateman-2026-agent-error-simulator-3c7d/
- Code: https://github.com/Keith-Bateman/agent-error-simulator
- Evidence used: controlled format, logic and tool-call injection; 194 jobs in abstract/table; four open models; role/step effects; final aggregator failure.
- Caveat: deterministic Riemann integration task; paper contains a 194/198 internal count discrepancy and reports 184 completed results after 10 failures.

## Preprints

### Zhang et al. — When Agentic Executions Fail: Detecting and Localizing Runtime Faults from Telemetry (AgentChaosBench)
- arXiv: https://arxiv.org/abs/2608.14680
- Date: 2026-08-04.
- Evidence: 275 traces, five systems, ten fault types, low zero-shot fault-type and localization accuracy.
- Caveat: five aligned inputs per condition; rule-based and specialized detectors left for future work.

### Zhan et al. — Airlock: Bounding the Multi-Agent Blast Radius via Selective Online Containment
- arXiv: https://arxiv.org/abs/2611.06727
- Date: 2026-11-04.
- Code announced: https://github.com/EdgeCitadelTeam/EdgeCitadel
- Evidence: provenance DAG, authority tree, per-object switches, full quarantine and deadline-aware minimum cut.
- Caveats: initial fault-origin set is supplied; trusted computing base; adaptive evasion excluded; no agent-memory rollback; coordinator saturation at roughly ten agents across three hosts; symptom-only root-cause localization is limited.

### Chintada et al. — ResonAct: Streaming Metrics for Runtime Diagnosis and Self-Healing in Multi-Agent Systems
- arXiv: https://arxiv.org/abs/2609.34701
- Date: 2026-09-28.
- Evidence: streaming telemetry, runtime diagnosis, policy-driven remediation; completion gains and measured recovery rates.
- Caveat: workload-dependent false positives; recovery denominator differs from retry success; preprint.

### Kraishan — Loud Failures, Quiet Failures: Fault Detection and Recovery in Tool-Using Language Model Agents
- arXiv: https://arxiv.org/abs/2610.10062
- Date: 2026-10-07.
- Code/data: https://github.com/obadaKraishan/brittle-agents
- Evidence: 1,920 trials, explicit vs silent fault detection, no-fault reporting, run-to-run variance.
- Caveat: 24 multi-step tasks and four injected fault types; preprint.

### Tunçtürk et al. — More Agents, More Reliable? System-Level Reliability of Multi-Agent LLMs under Operational-Profile Uncertainty
- arXiv: https://arxiv.org/abs/2611.07140
- Date: 2026-11-04.
- Status: submitted for IEEE Software; preprint at this pass.
- Evidence: interval-valued failure probabilities, Bayesian system failure logic, voter failure sensitivity.
- Caveat: one regulated chemical-hazard extraction pipeline.

### Kim et al. — Revisiting Continual Learning in Language Models: A Three-Interface Diagnosis of Stability and Plasticity
- arXiv: https://arxiv.org/abs/2611.30151
- Date: 2026-11-23.
- Evidence: trained-head, probe and backbone diagnostics; readout mismatch versus representation drift.
- Caveat: class-incremental encoder/decoder experiments, not a multi-agent organ-repair benchmark.

## Cross-pass references used for interpretation, not counted as new discoveries
- HiddenBench, ICML 2026: https://proceedings.mlr.press/v306/li26ej.html
- MAP-Graph, arXiv:2608.10509: https://arxiv.org/abs/2608.10509
- Pass 38 common-mode and diversity records.
- Pass 35 memory revocation and recovery records.
