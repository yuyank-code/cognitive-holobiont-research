# Research Log

## 2026-09-01 — Repository initialization

- Dedicated repository created by the user.
- Research mandate established as a long-horizon, adversarial, evidence-driven investigation.
- Treatise designated as the originating hypothesis/specification.
- Master index created.
- Research questions framework created.
- Claim–evidence matrix initialized.
- Contradiction log initialized.
- Open-problems register initialized.
- Falsification framework initialized.

### 2026-09-01 — First substantive literature pass

- Investigated latent-space inter-agent communication, hypernetworks, MoE, deep ensembles/uncertainty, consensus/BFT, and model compression.
- Found recent direct evidence that latent inter-agent communication is feasible, but the stronger claim of genuinely novel information transfer remains unresolved.
- Confirmed hypernetworks as an established weight-generation mechanism while finding no evidence yet for unrestricted, high-fidelity regeneration of arbitrary large specialists from compact shadow copies.
- Identified modern MoE as the strongest baseline for specialization + routing + conditional computation; Holobiont novelty therefore requires stronger architectural properties.
- Strengthened the importance of independent diversity for uncertainty and fault tolerance.
- Identified correlated epistemic failure as a direct threat to consensus-based truth claims.
- Elevated the shared-structure versus independent-structure tension to a primary experimental question.
- Added five priority falsification experiments to the literature map.

### 2026-09-01 — Second substantive literature pass

- Representation alignment: multi-way alignment work indicates that independently trained representations can be mapped into a shared reference space, but strict geometric alignment is not universally optimal. This strengthens the possibility of a common latent interface while warning against assuming a single canonical latent geometry.
- Model stitching: studies show useful interchangeability across representations and even across different architectures, supporting functional interface research rather than requiring identical internal representations.
- Latent collaboration: recent latent-agent systems report substantial benchmark gains and lower communication cost, but these are feasibility/engineering results, not causal proof that latent communication transmits information unavailable to the receiver's own model.
- Hypernetworks: task-conditioned hypernetworks can store many task-specific weight realizations in a compressed regime. This is meaningful evidence for compact parameter generation, but it does not establish arbitrary specialist reconstruction or preservation of OOD/robustness properties.
- Parameter-efficient adaptation: LoRA strengthens the case that a shared base plus small task-specific deltas can provide strong specialization. This is an important alternative explanation for parts of the proposed Holobiont design: a common base plus independent adapters may capture some benefits without full organ-level independence.
- MoE: Switch Transformer demonstrates that sparse expert specialization and routing already scale to very large parameter counts, while other work shows routing/consistency choices can materially change expert behavior. The Holobiont needs to demonstrate advantages beyond routing-based conditional computation.
- Recursive self-improvement: recent self-referential and self-improving agent work provides evidence that iterative self-modification can improve benchmark performance, but current results remain bounded by evaluation environments and do not establish safe open-ended recursive rearchitecture.

### Second-pass conclusions

1. The strongest near-term scientific opportunity is not proving that each component is individually novel; it is testing whether their combination creates a measurable capability that cannot be obtained by a shared backbone + adapters, MoE, ensemble, or multi-agent baseline.
2. The central design tension is now sharper: shared parameters and representations reduce communication and regeneration cost, but shared causes also increase correlated failure risk.
3. Latent communication should be studied with causal information-isolation experiments, not only downstream accuracy.
4. Regeneration should be evaluated as recovery of a specialist's behavior distribution, robustness, calibration, and latent representations—not merely benchmark accuracy.
5. Consensus should be evaluated under correlated errors and adversarial specialists, not only independent model ensembles.

### 2026-09-01 — Third/fourth substantive literature passes

- Biological neural communication provides precedent for task-relevant information transfer, but does not establish arbitrary shared high-dimensional cognitive latent spaces.
- Hypernetwork and self-healing results support a hierarchy of regeneration: checkpoint recovery, adapter regeneration, module regeneration, and full specialist reconstruction. Evidence is much stronger at the lower levels.
- Modular self-healing neural networks are now an explicit baseline, so self-repair alone is not a sufficient novelty claim.
- Weight-space diversity does not reliably imply functional diversity; future experiments must measure correlated behavior and failure, not just parameter distance.
- The strongest possible Holobiont advantage may be distributed recovery of capabilities unavailable to any surviving component alone.

### 2026-09-01 — Fifth substantive literature pass

- ACL 2026 ConSensus reports 7.1% average gains from specialized multimodal agents plus hybrid fusion, supporting heterogeneous specialization and fusion but not truth guarantees.
- ACL 2025 CONSENSAGENT and related 2026 work identify sycophancy and error cascades as serious multi-agent failure modes; Free-MAD explicitly removes consensus to avoid conformity and majority-vote weaknesses.
- 2026 work on multi-agent collusion demonstrates that open-channel agents can coordinate belief manipulation, strengthening the requirement for an immune/security layer.
- N-Version Programming with Coding Agents (2026) provides direct modern evidence that diversity can reduce failures while substantial common-mode failures persist. Nominal independence is therefore not a valid proxy for failure independence.
- A 2026 survey of 1,250 arXiv papers separates bounded self-refinement from open-ended recursive self-improvement and identifies grounding, evaluator reliability, collapse dynamics, and compute as persistent limits.
- Recursive Harness Self-Improvement shows bounded harness evolution can improve performance, but an independent open reproduction reports only partial replication and regression after further iterations. This is important negative/replication evidence.
- Recuris demonstrates bounded recursive memory evolution with strong long-horizon benchmark gains, making evolving memory a more credible near-term mechanism than unrestricted self-rearchitecture.
- AI4AI-Bench directly measures algorithm-design self-improvement and finds current agents remain far from the task optimum, strengthening the distinction between bounded improvement and genuine recursive improvement of the learning process.

### Fifth-pass conclusions

1. Consensus should no longer be modeled as intrinsically truth-seeking; it is an aggregation mechanism whose value depends on diversity, reliability estimation, and resistance to conformity/collusion.
2. Fault tolerance must be parameterized by measured failure correlation, not number of organs.
3. Recursive improvement should be decomposed into output refinement, memory/harness evolution, model-parameter modification, architecture modification, and learning-algorithm modification. Evidence strength falls sharply as the loop becomes more fundamental.
4. The most promising near-term Holobiont mechanism may be distributed memory/skill evolution plus modular repair, while unrestricted self-rearchitecture remains a speculative endpoint.

### Next research priorities

1. Extract every substantive claim from the treatise and map each to a claim ID.
2. Build the seminal-literature map for each major subsystem.
3. Follow citation chains from the treatise's suggested related work.
4. Identify competing architectures and terminology that may conceal equivalent prior work.
5. Investigate causal tests for novel information transfer in latent communication.
6. Quantify information-theoretic limits of specialist regeneration.
7. Model correlated failure as a function of shared parameters, training data, shared memory, and shared repair mechanisms.
8. Compare Holobiont against modern MoE, ensembles, multi-agent debate, modular networks, and self-healing approaches under matched compute.
9. Investigate whether shared-base + independent LoRA/adapters is a strong simpler baseline.
10. Reproduce key recursive-improvement claims under independent seeds and held-out evaluators.
11. Test whether distributed recovery can restore capabilities unavailable to any surviving component.
12. Do not begin implementation until the evidence and falsification framework justify it.
