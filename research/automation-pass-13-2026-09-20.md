# Automation Pass 13 — 2026-09-20

## Scope
Substantive follow-up on distributed information acquisition, coordination, adaptive communication, diversity preservation, and verification. The Treatise remains a hypothesis/specification rather than established fact.

## New evidence

### 1. Communication-reasoning gap remains the strongest negative result
SILO-BENCH (ACL 2026) evaluates 30 role-free algorithmic tasks across aggregation, mesh, and global-shuffle communication complexity, with 1,620 experiments. Agents communicate actively, but increasingly fail to turn interaction into correct distributed computation; high-complexity performance collapses at scale. This reinforces the distinction between information transport and computation/integration.
Source: https://aclanthology.org/2026.acl-long.1354/

### 2. Structural coupling can destroy the diversity that a Holobiont needs
Diversity Collapse in Multi-Agent LLM Systems (ACL 2026 Findings) reports diminishing diversity returns with group size and faster premature convergence under dense communication. The important update is that interaction topology itself can create common-mode cognitive failure, so independence must be treated as a resource rather than a static property of the underlying models.
Source: https://aclanthology.org/2026.findings-acl.13/

### 3. Coordination can be framed as resource allocation
ADAPT introduces message compression, dependency estimation, and auction-based dynamic prioritization. Separately, recent information/contract-design work shows that the value and optimal communication strategy for private information depends on receiver knowledge and incentive structure. These results support the information-market hypothesis, but they also show that utility-aware communication can introduce strategic and fairness problems.
Sources: https://journals.sagepub.com/doi/10.3233/FAIA251227 and https://www.ijcai.org/proceedings/2026/41

### 4. Dynamic topology is useful but not yet evidence of distributed computation
GoAgent explicitly constructs task-relevant groups rather than relying only on node-centric connectivity. This supports adaptive sparse topology as an engineering direction, while leaving the central causal question unresolved: does adaptive topology create unique collective computation after compute/communication costs are matched?
Source: https://www.alphaxiv.org/abs/2603.19677v1

### 5. Communication control is becoming certifiable
Consilience proposes conformally calibrated communication control for hidden-profile multi-agent reasoning, explicitly addressing the problem of deciding when communication is appropriate. This strengthens the architecture requirement for a communication controller that can abstain rather than always exchange messages.
Source: https://www.catalyzex.com/paper/consilience-conformally-calibrated

### 6. Memory is becoming a governed systems layer
SuperLocalMemory 4.0 reports fault-injection experiments for governed memory transactions, auditability, compensation, and erasure. These are component-level results, not proof of collective cognition, but they support treating distributed memory as a reliability/control-plane problem rather than merely retrieval.
Source: https://arxiv.org/abs/2608.08253

## Claim-evidence updates

- CH-002 (communication enables collective computation): **Partially supported / strongly constrained**. Communication is feasible; reliable distributed computation remains unproven and is contradicted by several controlled benchmarks at scale.
- CH-003 (latent/hidden-state communication): **Strongly supported as a mechanism, conditional as a scientific advantage**. The unresolved issue is causal unique information contribution under matched budgets.
- CH-006 (independence/resilience): **Partially supported, with a stronger negative interaction effect**. Dense communication can reduce diversity and create common-mode failure.
- CH-008 (adaptive topology): **Plausible / increasingly supported engineering hypothesis**. Dynamic topology methods exist, but collective computational advantage has not been isolated causally.
- CH-009 (information-market coordination): **Plausible hypothesis**. Dependency-aware prioritization and incentive-aware information exchange provide supporting mechanisms, but no evidence yet demonstrates positive coalition synergy under strict matched baselines.
- CH-010 (distributed memory as resilience infrastructure): **Partially supported** at the systems/component level; end-to-end cognitive resilience remains unestablished.

## New contradiction
A system can simultaneously improve communication efficiency and become less collectively capable if compression or coupling removes disagreement/independent evidence. Therefore, communication cost cannot be optimized independently of epistemic independence.

## Open problem
Define and measure **marginal epistemic contribution** of an agent: the improvement in conditional task-relevant information attributable to its private state after accounting for information already available to the coalition. Raw message length, embedding diversity, and answer diversity are insufficient proxies.

## Mathematical refinement
Let C be the coalition state before a communication action from agent i, M_i its proposed message, and Y the task-relevant target. Define:

U_i = I(Y; M_i | C) - lambda_c Cost(M_i) - lambda_k Coupling(M_i) - lambda_r Risk_i(M_i) - lambda_v Verify(M_i)

But the research target should additionally include coalition synergy:

S = I(Y; C_all) - max_{B in baseline-family} I(Y; B)

with B constrained to equal total compute, communication bandwidth, memory, and verification budget. A positive S is necessary but not sufficient for a Holobiont claim; it must persist under ablations removing adaptive routing, private information partitioning, and communication.

## Stronger falsification protocol
1. Construct tasks where each specialist holds non-overlapping but jointly necessary information.
2. Match total model FLOPs/parameters, context, communication tokens/bits, memory, and verifier budget across Holobiont, centralized, MoE, and conventional MAS baselines.
3. Measure pre-communication private information, post-communication information gain, integration accuracy, and termination reliability separately.
4. Randomize or substitute messages to test whether reported gains depend on example-specific sender information.
5. Force topology perturbations and agent failures to measure resilience and common-mode failure.
6. Test dense vs sparse vs adaptive communication to determine whether topology itself causes the gain.
7. Require replication across task families, seeds, model families, and independent evaluators.

## Architecture conclusion
The strongest current architecture is:

private heterogeneous specialists → capability-aware routing → active information-request protocol → sparse adaptive topology → causal communication interface → provenance/integrity layer → dependency-aware integration → independent verification → task anchor/termination → distributed governed memory → bounded repair → validation-gated reconfiguration.

The architecture should preserve **epistemic independence until the point at which integration requires coupling**. This is now a central design constraint, not a secondary optimization.

## Research frontier
The next decisive question is no longer whether agents can communicate. It is whether an adaptive protocol can allocate communication so that a coalition extracts **unique, conditionally useful information** and converts it into reliable distributed computation while preserving enough independence to avoid correlated failure.
