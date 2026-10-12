# Cognitive Holobiont Research — Pass 24
**Date: 2026-10-13**

## Executive result
This pass adds a mechanism-level benchmark under partial observability and corrects an earlier overgeneralization about memory contamination. The best current framing is a mechanism-switching evidence steward across (1) information acquisition/routing, (2) memory admission/temporal validity, and (3) causal evaluation of actions and outcomes. This remains a research hypothesis; Holobiont-specific synergy is unvalidated.

## 1. MASBench: new mechanism-level evidence
MASBench v1 (submitted 2026-10-03; public preprint) evaluates 600 instances across distributed-evidence reasoning, privacy-constrained scheduling, and cooperative grid-world tasks. It varies protocol, memory, and routing and uses task-grounded deterministic scores.

Reported results:
- In reasoning, structured protocol improves scores by about 1.5–28.4% across tested backbones while reducing message-token volume by 45.0–72.7%; score per communication token rises 2.0–4.2x.
- In scheduling, memory helps retain candidate/rejected slots; explicit proposal/vote/aggregation phases improve successful agreement in most tested backbones.
- In grid-world, Gate routing (decide whether to communicate, then select recipient) beats random recipient selection by 2.35–6.57 score points and reduces message tokens by 28.0–35.6%.

Limits matter: this is a new preprint. The reasoning comparison is protocolized multi-agent dialogue versus free-form multi-agent dialogue, not a fully matched single-agent baseline. Its communication metric excludes local reasoning, prompt tokens, and some non-transmitted generation. Framework-level comparisons change multiple implementation details and do not isolate a pure framework effect. Thus MASBench supports targeted protocol/routing/memory ablations, not a claim of unique collective cognition.

## 2. Material correction: Memory Contagion v2
The revised v2 paper narrows the earlier claim:
- Length-preference bias propagated under oracle consolidation for the tested older DeepSeek V4-Chat condition (reported Wasserstein distance 13.18; three seeds).
- LLM consolidation attenuated the measured effect to 2.03 in that condition, not to zero.
- Newer tested DeepSeek V4-Pro and an exploratory Claude Sonnet 4.6 run showed no detected length-bias contagion.
- Authority bias was zero in all 15 controlled multi-seed replications. An earlier large single-run result was explicitly classified as non-replicable exploratory evidence.

Therefore, earlier wording implying confirmed authority-bias propagation/amplification must be withdrawn. The defensible claim is conditional source-induced behavioral drift for some bias/model/measurement conditions; it is not universal. The “20% contamination” observation applies to the susceptible length-bias condition, not all bias types.

## 3. Memory governance and topology
TRACE distinguishes memory retrieval from action-time eligibility after shared state changes. It reports high valid-information retention and stale-information rejection in a constructed return benchmark, but some gains on STALE Type II cost about 2.3x tokens; a write-time consolidation pipeline is more accurate at about 3.99x TRACE's token cost. Treat it as a quality/cost frontier, not a universal winner.

The origin-bound memory-authority preprint argues that lineage/content checks can be laundered through summaries, trusted-tool echoes, and manufactured corroboration. Its reported zero attack success is specific to its tested attacks and models. It motivates write-time origin binding, not a universal security guarantee.

The 2025 EIB-Learner topology study uses counterfactual output interventions in six-agent GPT-3.5 systems: dense graphs spread useful insight and errors; very sparse graphs contain errors but can block useful information. Moderate sparsity often wins in those tasks. Do not treat any topology as universally optimal.

## 4. Literature map
- HiddenBench (ICML 2026, peer-reviewed): 65 hidden-profile tasks; 30.1% distributed-information multi-agent accuracy versus 80.7% for a single agent with the complete profile; structured communication improves performance in tested conditions.
- CRAFT (preprint): spatial coordination under partial views; individual reasoning quality does not reliably predict coordination.
- SILO-BENCH (ACL 2026, peer-reviewed): active communication can coexist with failure to integrate distributed state as complexity grows.
- MASBench (preprint): protocol, memory, and routing mechanism ablations.
- TRACE, Memory Contagion v2, MemEvoBench, Remembering More Risking More, and origin-bound memory authority: temporal validity, source bias, memory mis-evolution, long-horizon safety, and provenance laundering.
- Equal-thinking-token comparisons: single agents can match or outperform tested multi-agent systems on some multi-hop tasks.
- AgentWorld: long-horizon collaboration remains unreliable; graph-based contribution measures need intervention validation before causal interpretation.

Citation-chain synthesis: hidden-profile tasks isolate unspoken information asymmetry; role-free distributed computation exposes integration failures; MASBench makes protocol/memory/routing ablations more systematic; memory-governance work shows that acquired information can still be stale, biased, unauthorized, or laundered. Final accuracy alone cannot identify these failure causes.

## 5. Updated claim–evidence status
| Claim | Status |
|---|---|
| Communication volume alone solves distributed reasoning | Contradicted in naive form |
| Structured protocols can improve coordination efficiency | Supported in bounded settings |
| Selective routing can beat random routing | Supported in tested settings; generalization open |
| Memory is always beneficial | False as a universal claim; governance required |
| Perfect consolidation removes source bias | Contradicted for a susceptible length-bias condition |
| Authority bias reliably propagates through memory | Earlier broad claim withdrawn; v2 controlled replications were zero |
| Sparse topology is always better | Contradicted as a universal rule |
| Message-token efficiency equals total efficiency | False; several resource categories are excluded |
| Holobiont-specific causal synergy exceeds best alternatives | Unvalidated |

## 6. Contradictions and open problems
1. More communication can reveal private facts and spread errors.
2. Memory preserves state but can become stale or carry biased source experience.
3. Provenance lineage can be laundered unless origin/authority is bound before transformation.
4. Protocolized agreement is not proof of truth.
5. Sparse routing contains errors but may suppress valid minority evidence.
6. Message-token efficiency can hide increased reasoning, verification, tool, latency, or monetary costs.
7. Graph-based contribution is not causal without interventions.

Open questions: estimate governed value of information; propagate retractions to dependent actions; preserve valid minority evidence; generalize routing policy across task families; match budgets when internal reasoning is hidden; validate causal contribution under correlated failures; and test whether any Holobiont gain survives single-agent, ensemble-selection, MoE, and verified-shared-context baselines.

## 7. Falsification protocol
Compare best feasible single agent, full-information diagnostic, independent ensemble plus selection, fixed broadcast/round-robin, unrestricted debate, random routing, selective routing without memory governance, verified shared context, and adaptive elicitation with governed memory.

Randomize decisive-fact ownership; remove/delay/replace messages; ablate senders/receivers; inject stale, contradictory, biased, and origin-laundered memories; include valid minority facts; vary topology and agent count; replicate across seeds and hold out task families.

Match or report reasoning, message, prompt, memory, tool/API, verifier, latency, and monetary costs. If internal reasoning is hidden, mark it unobserved rather than claiming full matching. Measure task utility, unique-fact recovery, unauthorized disclosure, false admission/rejection, stale-descendant actions, memory drift, intervention-validated action contribution, and cost per correct result.

Reject Holobiont-specific synergy in any tested regime if its gain disappears against the strongest feasible baselines or is explained by extra information, compute, or verification.

## 8. Mathematics and architecture
Let \(\mathcal Q(G_t)\) be the set of policy-permitted queries under governance state \(G_t\). Define governed value of information:

\[
\operatorname{GVOI}(q)=\mathbb E[U\mid q,G_t]-\mathbb E[U\mid G_t]
-\lambda_b B(q)-\lambda_\ell L(q)-\lambda_v V(q)-\lambda_p P(q),
\quad q\in\mathcal Q(G_t).
\]

Represent memory item \(z=(c,o,t_w,s,v,\pi,\mathcal P,\mathcal C,\mathcal D)\): claim, write-time origin, write time, scope, validity/version, provenance, parent evidence, contradictions, and dependent claims/actions. Action-time eligibility requires authorization, scope validity, temporal validity, and valid origin authority. Retraction triggers descendant re-evaluation without deleting independent corroboration.

The provisional synergy target is the coupled system's task utility minus the best feasible matched baseline, under a resource vector covering reasoning, messages, prompts, memory, tools, verification, latency, and money. Require sender/message/action interventions and held-out replication.

Candidate architecture: independent exploration → epistemic state → missing-information inference → authorized query → typed response or verified shared-context update → origin-bound admission → temporal eligibility/contradiction handling → independent challenge → action-grounded verification → retraction and descendant re-evaluation → termination or safe fallback. The controller must be able to choose private routing, shared context, challenge, no-op, quarantine, or abstention. No implementation is recommended yet.

The originating PDF remains a hypothesis/specification. Hypernetwork regeneration, consensus-loss immunity, entropy reduction as correctness, and recursive self-rearchitecture remain unvalidated.
