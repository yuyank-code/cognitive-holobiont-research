# Cognitive Holobiont Research — Pass 17 (2026-09-24)

## Scope

This pass treats the originating PDF/treatise as a hypothesis/specification, not established fact. It follows recent open literature on distributed computation, adaptive topology, information-bottleneck communication, shared verified state, and causal/emergent coordination. Prior conclusions are preserved unless stronger evidence changes them.

## Executive finding

The evidence now supports a narrower positive claim: **adaptive communication control and structured shared state can materially improve multi-agent coordination, but this still does not establish a general Holobiont-level positive coalition synergy mechanism.** The most important new development is that several independent 2026 systems now converge on the same control pattern: estimate information need, route selectively, constrain bandwidth, maintain verified shared state, and enforce a commit/termination protocol.

This is important because it turns the research target from an unconstrained “collective intelligence” problem into a testable **epistemic control problem**. However, the strongest negative evidence remains: SILO-BENCH finds active communication with failure at distributed integration; MAS-BENCH finds scaling failures in shared state, conventions, and termination. These results remain the primary falsification pressure.

## New literature findings

### 1. MAS-BENCH + CAMOC: structured state can repair part of the integration failure

MAS-BENCH evaluates distributed sorting under explicit communication constraints and reports sharp degradation as agent count increases, with failures in shared state, convention alignment, and termination. Its CAMOC intervention—collaboration-aware information sharing, early global metadata exchange, and single-commit verification—substantially improves coordination success and efficiency, especially with shared state.

Interpretation: this is a meaningful **positive counterexample to the strongest pessimistic reading** of SILO-BENCH. Coordination failures are not necessarily intrinsic to multi-agent decomposition; protocol structure can recover some performance. But CAMOC is a proof-of-concept on a specific distributed sorting task, not evidence for general positive coalition synergy. The gain must be decomposed into information availability, synchronization, and verification effects before attributing it to a Holobiont mechanism.

Source: Yang et al., “When 20 Agents Fail to Sort,” Findings of ACL 2026.

### 2. Consilience: communication control itself may be the useful primitive

Consilience uses a compact state containing uncertainty, disagreement, evidence gain, redundancy, and premature-consensus signals to choose among challenge, clarify, seek-evidence, and routing actions. It reports improved accuracy/communication efficiency on hidden-profile tasks, with some results surpassing a full-information baseline.

Interpretation: this is the strongest new evidence for the prior governed-epistemic-scheduler direction. The important object is not message volume or latent bandwidth, but **action selection conditioned on epistemic state**. The full-information comparison is especially important because it suggests that better control can sometimes compensate for not exposing all information. This supports the hypothesis that selective acquisition can be more valuable than indiscriminate sharing.

Caution: the reported guarantee is a calibrated one-step regret bound under its calibration assumptions; it is not a guarantee of global collective optimality or resilience.

Source: Babu et al., “Consilience: Conformally Calibrated Communication Control for Hidden-Profile Multi-Agent Reasoning,” arXiv, Aug. 2026.

### 3. MANTA / DyTopo / TopoDIM: adaptive topology is becoming an established design axis

MANTA adapts communication structure at inference time while preserving an agent budget; DyTopo reconstructs sparse directed graphs from round-specific information needs and offers; TopoDIM generates heterogeneous interaction topologies with lower token use and modest performance gains.

Interpretation: adaptive topology is no longer merely speculative architecture rhetoric. There is convergent engineering evidence that task- and round-conditioned topology can improve efficiency/performance. However, these results do not yet show that topology changes create *causal coalition synergy* rather than better orchestration.

### 4. Heterogeneous Information-Bottleneck Coordination Graphs: a mathematical route to topology + bandwidth allocation

HIBCG explicitly couples graph sparsity and message capacity under an information-bottleneck objective and derives group-dependent edge retention and water-filling-style capacity allocation.

Interpretation: this is useful mathematical support for the Holobiont objective. It suggests replacing an undifferentiated communication penalty with a joint optimization over edge existence and channel capacity. But the work is primarily cooperative MARL rather than LLM cognition, so transfer must be tested rather than assumed.

### 5. DeLM: decentralization plus verified shared context is a serious competing architecture

DeLM decentralizes coordination using asynchronous task claiming, a shared verified context, and a task queue. It reports improvements in software-engineering test-time scaling and long-context reasoning.

Interpretation: this is an important competing architecture to the “private specialists + selective routing” formulation. A Holobiont must therefore beat or complement **verified shared-state decentralization**, not merely a centralized orchestrator. Otherwise the proposed architecture may be overcomplicated relative to a simpler shared-context system.

### 6. Emergent Coordination: possible positive synergy, but measurement is the issue

A 2026 study proposes information-theoretic measures based on partial information decomposition of time-delayed mutual information and reports identity-linked differentiation and goal-directed complementarity in prompted multi-agent groups.

Interpretation: this is the most relevant new evidence on the positive side of the “higher-order collective” question. It provides a route for distinguishing temporal coupling from performance-relevant synergy. But the experimental setting is limited and should not be treated as proof of general distributed computation.

### 7. Negative/security evidence remains active

SILO-BENCH remains the strongest distributed-computation negative result. Diversity-collapse work continues to show that dense interaction can destroy useful independence. AgentLeak and latent KV-cache integrity work show that internal channels create security/privacy surfaces invisible to final-output evaluation.

## Revised claim-evidence matrix

| Claim | Pass 17 evidence | Updated status |
|---|---|---|
| C1: communication alone enables distributed computation | SILO-BENCH + MAS-BENCH failures | **Contradicted in naive form** |
| C1b: structured coordination can recover some distributed computation | CAMOC, Consilience | **Partially supported** |
| C2: latent/hidden communication is sufficient for collective computation | StateBridge shows transport utility; no general computation proof | **Unvalidated** |
| C3: preserve epistemic independence/diversity | Diversity Collapse; representational-collapse evidence | **Conditionally supported** |
| C4: topology should adapt to task/round epistemic state | MANTA, DyTopo, TopoDIM, HIBCG | **Strongly supported as design hypothesis; causal cognitive benefit unvalidated** |
| C5: information value should be receiver-context dependent | Consilience + information-bottleneck literature | **Plausible / increasingly supported** |
| C6: verified shared state can outperform pure message passing | MAS-BENCH/CAMOC; DeLM | **Partially supported** |
| C7: governance must cover internal channels | AgentLeak + KV integrity | **Strongly supported as systems requirement** |
| C8: Holobiont creates positive coalition synergy from complementary private information | Emergent Coordination gives measurement ideas, but no decisive distributed-computation proof | **Key open hypothesis** |
| C9: coalition-level resilience can exceed centralized baselines | No decisive evidence found | **Unsupported / key falsification target** |

## Contradictions to preserve

1. **Communication helps vs. communication harms.** CAMOC/Consilience/MANTA show that structured communication can help; SILO-BENCH and diversity-collapse work show that communication can fail or reduce useful diversity. Resolution: communication value is state-, topology-, and task-dependent.
2. **Decentralization vs. central control.** DeLM suggests shared verified state can remove a central bottleneck; other adaptive-topology systems use managers/controllers. The Holobiont should not assume decentralization is intrinsically superior.
3. **More information vs. selective information.** Full-information access is not automatically optimal; selective, calibrated communication can be competitive. This challenges any architecture that maximizes latent bandwidth.
4. **Shared state vs. epistemic independence.** Shared verified state can repair integration failures but can also become a convergence/correlation channel. Verification and independence must be measured jointly.
5. **Latent interoperability vs. governance.** Hidden-state transport can improve information flow while making provenance, inspection, and tamper detection harder.

## Revised mathematical formulation

Let coalition state be \(S_t\), task target \(Y\), and candidate action \(a\) be one of {ask, share, preserve, challenge, route, quarantine, terminate}. For candidate communication from agent i to receiver j, define:

\[
U_{ij}(a_t) = \Delta I(Y;S_{t+1}\mid S_t) - \lambda_B B - \lambda_T T - \lambda_C C - \lambda_D D - \lambda_G G - \lambda_R R.
\]

Where:

- \(\Delta I\): estimated conditional information gain about the task target;
- \(B\): bandwidth/token/latent-channel cost;
- \(T\): latency or synchronization cost;
- \(C\): coupling cost, including loss of independent hypotheses;
- \(D\): redundancy/dependence cost;
- \(G\): governance/privacy/provenance risk;
- \(R\): correlated-failure/adversarial risk.

For coalition synergy, define an intervention-based quantity rather than a raw accuracy gap:

\[
\Gamma = P(Y\mid \text{coalition},\mathcal B) - \max_{A\in\mathcal B}P(Y\mid A),
\]

where \(\mathcal B\) denotes matched compute, memory, bandwidth, verifier, and information-access budgets. A stronger test uses private-information ownership permutations and sender ablations. Positive \(\Gamma\) is necessary but not sufficient: the gain must disappear when the unique complementary information is removed or randomized.

A new causal synergy score should therefore be:

\[
\Gamma_{causal}=\Delta Perf(\text{coalition})-\Delta Perf(\text{coalition with unique-info intervention}).
\]

The architecture should only claim genuine distributed cognition if the observed gain is attributable to conditionally useful information exchange rather than extra compute, voting, decomposition, or verifier capacity.

## Falsification framework — strengthened

A future decisive benchmark should include:

1. **Private-information partitioning:** each agent owns non-overlapping evidence necessary for the target.
2. **Ownership swap:** permute which specialist owns which evidence.
3. **Sender ablation:** remove or corrupt one information owner and measure degradation.
4. **Topology intervention:** randomize/rewire edges while preserving degree and bandwidth.
5. **Communication intervention:** compare full broadcast, fixed schedule, adaptive scheduler, and no communication.
6. **Shared-state control:** compare message passing with verified shared context and with stale/mutable shared state.
7. **Compute-matched centralized baseline:** allow the centralized model equal total inference compute.
8. **Information-matched baseline:** give the centralized model the same evidence but preserve the distributed system's total token budget.
9. **Verifier-matched baseline:** equalize verification calls and model capacity.
10. **Adversarial/noisy-agent tests:** inject misinformation, stale state, collusion, or compromised internal channels.
11. **Diversity measurement:** measure representation/output diversity before and after communication.
12. **Termination test:** measure whether the system can identify when additional communication has negative expected value.
13. **Replication across task families:** algorithmic distributed computation, hidden-profile reasoning, planning, code, and information-seeking.

Failure of positive \(\Gamma_{causal}\) across these controls should count against the strong Holobiont hypothesis.

## Architecture conclusion

The current architecture is revised to:

**private heterogeneous specialists → epistemic-state estimation → adaptive action scheduler → sparse topology / verified shared context → causal communication interface → provenance + authorization + privacy → dependency-aware integration → independent verification → task anchoring + termination → governed distributed memory → bounded repair → validation-gated reconfiguration**

The important revision is that **verified shared context is now a competing first-class substrate**, not merely an implementation detail. The scheduler should be able to choose between direct private routing and shared verified state depending on expected information value and coupling risk.

## Open problems

- Can coalition synergy be causally separated from extra inference compute?
- Can a scheduler estimate marginal information value reliably without already solving the task?
- When does shared verified context outperform private selective routing?
- Can latent communication preserve provenance and integrity at useful cost?
- Can independence be preserved while still enabling fast integration?
- Can positive coalition synergy survive adversarial and common-mode failures?
- Is the synergy signal from partial-information decomposition predictive of exact distributed-computation success?
- Can adaptive topology improve robustness, not merely benchmark score?

## Bottom line

The evidence has moved the program forward, but not toward implementation. The strongest defensible conclusion is now:

> **The promising object is a governed epistemic control system that adaptively allocates information flow and shared state while preserving useful independence. The existence of general Holobiont-level cognitive synergy remains unproven.**

The next high-value research step is a direct synthesis of SILO-BENCH/MAS-BENCH-style exact distributed computation with hidden-profile private-information tasks and causal topology/communication interventions. That experiment should be designed before any production architecture is implemented.
