# Claim–Evidence Matrix — Pass 41 Addendum

| Holobiont claim | New evidence | Status after Pass 41 | Boundary / missing proof |
|---|---|---|---|
| Organs can detect their own and peers' failures | AgentChaosBench; Loud Failures/Quiet Failures; ResonAct | Partial / weak | Silent semantic faults remain difficult; detector precision and recall vary by workload; false positives can be large |
| A faulty organ can be isolated before its output harms others | Airlock | Supported after a valid origin alert in bounded systems | Initial origin set is supplied; trusted runtime and gateway; adaptive evasion excluded |
| Downstream contamination can be traced | Airlock provenance DAG | Promising, conditional | Symptom-only root localization is uncertain; memory rollback/repair is outside current Airlock scope |
| Workers can self-correct faults | AES | Conditional | Non-final tool/format faults recover in the test; semantic logic faults depend on model/role/step; final-step faults persist |
| The aggregator can safely integrate many organ outputs | AES | Contradicted as a default assumption | Aggregator arithmetic/context errors and injected aggregator faults can destroy correct worker outputs |
| Runtime monitors can improve task completion | ResonAct | Partial support | Recovery among detected failures only 10.48–46.67%; false-positive rates and overhead vary |
| More agents necessarily increase reliability | Operational-profile reliability paper | Not supported | Combiner, common-cause failures and workload mix can erase redundancy benefit |
| A repaired organ can safely rejoin shared memory | Pass 35 memory governance plus new runtime evidence | Open | Need end-to-end revocation, taint closure, state consistency and re-entry experiments |
| Apparent capability loss always means representation loss | Three-interface continual-learning diagnosis | Rejected | Head/readout mismatch can hide recoverable backbone information |
| The complete Holobiont is self-healing | Combined literature | Unproven | No end-to-end heterogeneous persistent federation has demonstrated detection → localization → containment → repair → independent validation → reintegration |

## New source records

1. Bateman et al., *Agent Error Simulator*, IEEE eScience 2026: https://doi.org/10.1109/eScience70237.2026.00052
2. Zhang et al., *When Agentic Executions Fail / AgentChaosBench*, arXiv:2608.14680: https://arxiv.org/abs/2608.14680
3. Zhan et al., *Airlock*, arXiv:2611.06727: https://arxiv.org/abs/2611.06727
4. Chintada et al., *ResonAct*, arXiv:2609.34701: https://arxiv.org/abs/2609.34701
5. Kraishan, *Loud Failures, Quiet Failures*, arXiv:2610.10062: https://arxiv.org/abs/2610.10062
6. Tunçtürk et al., *More Agents, More Reliable?*, arXiv:2611.07140: https://arxiv.org/abs/2611.07140
7. Kim et al., *Revisiting Continual Learning in Language Models*, arXiv:2611.30151: https://arxiv.org/abs/2611.30151
