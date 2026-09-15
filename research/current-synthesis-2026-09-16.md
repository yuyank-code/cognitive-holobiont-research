# Current Synthesis — 2026-09-16

## Major conclusion change
The research now separates four problems that were previously too easy to conflate: latent information transport, distributed information acquisition, distributed computation, and reliable integration. Latent transport is increasingly well supported; the hardest unresolved problem is making agents acquire complementary information and execute complementary computation without convergence, drift, or common-mode failure.

## Current claim status

| Claim | Status | Reason |
|---|---|---|
| Modular specialists are useful | Established | Broad modular/MoE literature |
| Heterogeneous latent communication is feasible | Strongly supported | Interlat, LatentMAS, StateBridge |
| Latent messages necessarily carry sender-specific task information | Partially supported | Causal audit shows effects can include non-example-specific information and vary by model/task |
| Communication alone yields distributed computation | Contradicted for naive scaling | SILO-BENCH, MAS-BENCH, HiddenBench |
| Agents will request missing information appropriately | Weak/partially supported | HiddenBench identifies latent-information-asymmetry failure |
| Selection/integration is a core bottleneck | Strongly supported principle | Debate, selection, diversity and routing studies |
| More agents imply more useful diversity | Contradicted as a general assumption | Diversity collapse and single-agent multi-output results |
| Adaptive selective communication is preferable to always-on interaction | Promising/strongly motivated | Drift, scaling and debate evidence plus selective-debate work |
| Latent payloads can be trusted without provenance/integrity | Contradicted as a security assumption | KV tampering can alter outcomes while visible text remains plausible |
| Hypernetworks regenerate unique lost capabilities | Unproven | Generation/adaptation evidence does not establish information recovery |
| Full Holobiont superiority | Unproven | No matched-resource end-to-end demonstration |

## Architectural consequence
The Holobiont should be modeled as a governed distributed information-processing network rather than a collection of communicating agents. A specialist must be able to (a) retain private state, (b) advertise/measure capabilities, (c) request specific missing evidence, (d) send selectively compressed information through an integrity-protected interface, (e) contribute to a verifiable distributed computation, and (f) abstain or terminate when expected information gain is insufficient.

## Mathematical direction
For sender i and receiver R, define unique conditional information:

I_i = I(Y; M_i | X, Z_R, M_{-i})

A system-level contribution measure should compare the joint conditional information against matched centralized baselines, while avoiding treating mutual information estimates as direct proof of useful reasoning. Controlled message substitution, permutation, and self-substitution are required.

For coordination efficiency:

DCE = Success / (Compute + alpha Communication + beta CoordinationRounds)

This is a benchmark-normalization proposal, not an established law.

A further target is information-acquisition regret: the loss caused by failing to request/reveal a fact that was available elsewhere in the group. This directly operationalizes the HiddenBench failure mode and may be more diagnostic than communication density.

## Highest-priority falsification experiment
Construct exact distributed algorithms with hidden partitions where no individual agent has sufficient information to solve the task. Compare:
1. single model with full information;
2. single model with partitioned information but serial self-conditioning;
3. MoE;
4. conventional text MAS;
5. latent MAS;
6. Holobiont candidate with capability routing + request/response protocol + causal provenance.

Equalize total input information, model compute, communication budget, and output budget. Require exact/verifiable answers. Measure success, unique sender contribution, information-acquisition regret, rounds, bandwidth, diversity collapse, drift, and robustness to one malicious or corrupted channel.

The result that would matter is not merely higher benchmark accuracy. The strongest evidence would be a regime in which the Holobiont solves distributed tasks that matched centralized/MoE/MAS baselines cannot, while retaining positive unique sender contribution and lower or comparable coordination cost.

## Next frontier
Research protocols for explicit information acquisition and compositional distributed algorithms. Follow citation chains from HiddenBench/MAS-BENCH/SILO-BENCH and latent communication work into distributed planning, blackboard/shared-memory coordination, algorithmic communication complexity, and verifier-backed multi-agent computation. Regeneration and consciousness remain secondary until the distributed-computation core is experimentally defensible.
