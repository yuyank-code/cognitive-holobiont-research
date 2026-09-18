# Automation Pass 12 — 2026-09-19

## Scope
Fresh pass on distributed information acquisition, decentralized coordination, adaptive topology, pragmatic communication under partial information, and verification. The treatise remains a hypothesis/specification.

## New evidence

### 1. DeLM supplies a positive counterpoint to the centralized-controller bottleneck
Decentralized Language Models (DeLM) use asynchronous agents, a shared verified context, and a task queue rather than a central scatter-gather controller. Reported experiments improve SWE-bench Verified and LongBench-v2 Multi-Doc QA while reducing reported cost per task. This is important because it demonstrates that structured shared state can improve practical coordination rather than merely increasing message traffic.

Limit: the reported gains do not yet establish irreducible distributed computation. Agents still operate through a shared context substrate and benchmark tasks; the causal contribution of decentralization versus task decomposition, verification, and shared-state design remains to be isolated.

### 2. Adaptive sparse topology is converging across independent approaches
DyTopo reconstructs a sparse directed communication graph each round from agent need/offer descriptors. GoAgent explicitly constructs task-relevant groups and applies an information-bottleneck objective to suppress redundant inter-group communication. RAPS frames adaptive coordination as intent-based publish/subscribe with reputation-aware filtering.

Implication: the Holobiont's dynamic topology idea is no longer speculative as a systems technique. The open problem is whether adaptive topology can preserve *functional independence* while improving collective computation and fault isolation.

### 3. CRAFT isolates pragmatic coordination from raw model intelligence
CRAFT gives multiple agents complementary private views of a 3D structure and requires them to communicate enough information for a builder to construct a globally correct state. Across frontier and open-weight models, stronger individual reasoning or communication quality does not reliably imply stronger collaboration. Its diagnostics separate spatial grounding, belief modeling, and pragmatic sufficiency.

Implication: a Holobiont evaluation should measure whether specialists know what is missing from the collective state, not merely whether each specialist reasons well in isolation.

### 4. Verification can be made trace-based rather than purely judge-based
MORPHAGENT reports metamorphic testing over structured multi-agent execution traces, detecting seeded coordination and goal-deviation faults without requiring a conventional ground-truth oracle. This suggests a useful verifier layer for the Holobiont: validate invariants of the *process/state transition*, not only the final answer.

Limit: metamorphic relations themselves can be incomplete or incorrect; trace validation is an additional oracle, not a proof of semantic correctness.

### 5. Shared verified context is simultaneously an opportunity and a common-mode risk
DeLM's shared verified context addresses the integration bottleneck, but it also concentrates state. A corrupted verification rule, stale shared state, or common representation can propagate across otherwise independent specialists. This reinforces the existing common-mode-failure concern rather than replacing it.

### 6. New synthesis: the missing primitive may be information-market coordination
Across HiddenBench/CRAFT/SILO-BENCH/MAS-BENCH and the positive topology work, the recurring problem is not merely sending messages. Agents need to estimate what information exists elsewhere, decide which information is worth acquiring, and avoid redundant or misleading transfers. This suggests an explicit information-market layer: agents expose claims about what they know, what they need, provenance, confidence, and expected utility; a controller or decentralized protocol allocates communication based on marginal information value.

This is a research hypothesis, not an established architecture.

## Updated mathematical direction

Let agent i possess private information S_i and receiver state Z_R. Define a communication action a_i selecting a payload M_i and a recipient set E_i. The marginal value of communication should be conditioned on the current collective state:

`V_i(a_i | Z_R) = E[U(Y_hat | Z_R, M_i) - U(Y_hat | Z_R)] - Cost(a_i)`

For a distributed task, define the *marginal unique information* of agent i as the performance drop under removal of S_i while preserving all other information and protocol state:

`U_i = U(H | S_1,...,S_N) - U(H | S_{-i})`.

This is closer to causal contribution than correlation. For coalitions, test submodularity/synergy rather than assuming additive contributions:

`Synergy(A,B) = U(H | A,B) - U(H | A) - U(H | B) + U_0`.

Positive synergy is especially important for a Holobiont claim because it would indicate that useful computation arises from combining independently held information rather than selecting the best isolated answer. These quantities require carefully matched counterfactual protocols and are proposed metrics, not established universal measures.

A communication policy should optimize something like:

`max_pi E[U] - beta * Bandwidth - gamma * Coupling - delta * FailureCorrelation - eta * VerificationCost`

subject to exact task constraints and a bound on total compute. The new term `Coupling` represents communication-induced dependence; it should be measured empirically rather than assumed.

## Claim-evidence updates

### CH-014 / CH-022 / CH-034
Adaptive sparse topology is now better supported as a practical mechanism. The evidence from DyTopo and GoAgent converges on task-dependent graph construction and information bottlenecking. However, topology utility does not establish safe autonomous self-reconfiguration or resilience.

### CH-025 / CH-028 / CH-037
Negative distributed-computation evidence remains intact, but the positive DeLM and CRAFT results show that structured state ownership, asynchronous progress, and pragmatic communication can narrow specific coordination failures. Therefore the stronger conclusion is: naive scaling is contradicted; structured coordination is promising but not yet a general solution.

### CH-031 / CH-032
Independent process verification and explicit task anchoring gain additional support from metamorphic testing and CRAFT's diagnostic decomposition.

### CH-041
Resource matching must now include not only compute and total communicated information, but also shared-state access, verification budget, and protocol complexity. Otherwise decentralized systems may receive hidden advantages from richer coordination infrastructure.

## Contradictions / adversarial evidence

- Positive DeLM results can be explained partly by shared verified state and task-queue engineering; decentralization itself is not isolated causally.
- Dynamic topology can improve average accuracy while increasing controller dependence or correlated failure.
- Information bottlenecks can remove redundancy that was actually useful for recovery.
- A verified shared context can amplify a single verification mistake across the whole population.
- CRAFT shows that high-quality individual communication can still fail to produce collective correctness.
- Trace-based metamorphic verification can miss failures outside its chosen invariants.

## Open problems added

1. Can an information-request policy identify *which absent private fact* is worth querying?
2. Can distributed agents estimate marginal unique information online without revealing all private state?
3. Can positive coalition synergy be demonstrated against a compute- and information-matched centralized model?
4. Does adaptive topology improve K_eff (effective independent channels) rather than merely reducing communication cost?
5. Can shared verified state be replicated without creating a common-mode verification failure?
6. What protocol permits decentralized termination with exact correctness guarantees on bounded algorithmic tasks?
7. Can metamorphic invariants be generated independently enough to avoid evaluator circularity?
8. Does latent communication improve information-market decisions compared with text under equal transmitted information?

## Falsification upgrades

A future Holobiont prototype should be rejected as genuine distributed computation if:

- it gains from shared-state access but loses the gain when state is replaced by equivalent centralized memory;
- its positive coalition synergy disappears when a centralized model receives the same total private information;
- adaptive topology improves performance only by increasing total information/compute beyond the baseline;
- removing a purported specialist's private information leaves collective performance unchanged;
- a common verification-state perturbation causes widespread synchronized errors;
- information-request decisions cannot beat random/request-all baselines at equal bandwidth;
- process-level metamorphic tests fail to predict held-out semantic failures better than final-answer judging;
- communication-induced coupling reduces effective independence enough to offset added specialists.

## Architecture conclusion

The strongest current architecture is evolving toward an **information market + modular computation substrate**:

`private specialists -> capability/need declarations -> marginal-information routing -> sparse typed communication -> shared verified state with provenance -> coalition computation -> independent verifier(s) -> task anchor/termination -> distributed capability traces -> bounded repair -> validation-gated reconfiguration`

The important novelty target is no longer “a network of AI organs.” It is whether such a system can create **measurable positive synergy from independently held information while maintaining independence, verification, and fault isolation**.

## Sources

- DeLM, 2026: https://arxiv.org/abs/2606.10662 and https://github.com/yuzhenmao/DeLM
- DyTopo, 2026: https://arxiv.org/abs/2602.06039
- GoAgent, 2026: https://arxiv.org/abs/2603.19677
- RAPS, 2026: https://arxiv.org/abs/2602.08009
- CRAFT, 2026: https://arxiv.org/abs/2603.25268 and https://github.com/csu-signal/CRAFT
- MORPHAGENT, IEEE AITest 2026: https://ieeexplore.ieee.org/abstract/document/11662476/
- SILO-BENCH, ACL 2026: https://aclanthology.org/2026.acl-long.1354/
- MAS-BENCH, Findings ACL 2026: https://aclanthology.org/2026.findings-acl.1698/
- Beyond tokens, 2026: https://arxiv.org/abs/2606.05711
