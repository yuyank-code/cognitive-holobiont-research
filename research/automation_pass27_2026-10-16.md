# Cognitive Holobiont Research — Pass 27
**Research date:** 2026-10-16  
**Scope:** Causal evaluation of collective synergy, topology-aware confidence, and fault recovery. Literature synthesis only; no implementation recommended.

## Executive finding

This pass strengthens a more precise claim than “multi-agent systems work” or “multi-agent systems fail”: **collaboration has measurable, task-conditional value, but neither consensus, communication volume, an interaction graph, nor an information-theoretic synergy score alone proves that a collective is more capable.**

Four useful evidence strands now connect:

1. **Causal counterfactuals for agent dependence.** CAGE-Cal compares an interacting panel with matched no-communication runs of the same agents. On five benchmarks and five topologies, its preprint reports better panel-correctness discrimination than scalar disagreement/confidence baselines, and its CAGE-Select policy improves mean accuracy by 2.05 percentage points over the best fixed topology in its tested setting.
2. **Information-theoretic emergence can be measured, but its task-general meaning remains open.** The ICLR 2026 paper *Emergent Coordination in Multi-Agent Language Models* uses randomized prompt interventions and partial-information decomposition to distinguish complementary information from mere temporal coupling. Its experiments are confined to a simple group guessing game; the authors explicitly say the link from synergy measures to performance is difficult and needs more tasks.
3. **Long-horizon collaboration can outperform a single-agent baseline in a deliberately collaborative environment.** AgentWorld reports 52.0% task success for its strongest primary model versus 28.6% for its single-agent baseline, and 60.0% with an oracle-communication condition. But the best reported causal-collaboration-effectiveness score is 0.320, and the benchmark remains a particular sandbox with an LLM-assisted action-attribution metric.
4. **Architecture and fault handling matter independently of backbone strength.** MAS-FIRE’s fault-injection experiments show large differences between linear and iterative closed-loop workflows for selected injected faults. MARS and MASBench provide complementary evidence that structured, mostly independent review, typed protocols, memory, and selective routing can reduce communication waste in tested tasks.

These findings refine the hypothesis, not validate the full Cognitive Holobiont. The PDF remains a proposed specification. Claims about a novel general-purpose collective cognition, latent “brain-to-brain” communication, regeneration of erased specialist capability, consciousness, or indefinite survival remain unestablished.

## 1. Counterfactual calibration: agreement is not independent evidence

Huang et al., *Counterfactual Graph for Multi-Agent LLM Calibration* (arXiv:2605.30653, preprint submitted 2026-05-28), studies two opposite errors in panel confidence: reliable diversity can look under-confident, while communication-induced correlated mistakes can create false consensus. CAGE-Cal constructs a graph from the panel after communication and a matched independent/no-communication counterfactual graph using the same agent identities. It models pairwise error dependence plus higher-order groupings such as model family, prompt role, answer cluster, and topology.

Reported results include:
- On the five benchmark suite, in-distribution mean ECE 5.56 and mean AUROC 83.61, compared with 7.08 and 73.46 for the strongest trained baseline named in the paper.
- Under leave-one-topology-out evaluation, mean ECE 6.56 and AUROC 82.21, suggesting some transfer to an unseen topology in this experimental setup.
- CAGE-Select reaches 67.23% mean accuracy versus 65.18% for the best fixed topology, a 2.05-point gain in the reported comparison.

These are promising results, not a universal calibrated-confidence solution. There are three important caveats. First, this is a preprint with three rollouts reported for major comparisons. Second, its panel is drawn from a predefined agent pool; the authors state that agent participation and communication are not jointly optimized. Third, obtaining independent counterfactual panel runs and evaluating multiple candidate topologies incurs extra computation. A deployment comparison must charge those runs and must check calibration shift on held-out tasks, model families, and adversarially correlated agents.

Source: https://arxiv.org/abs/2605.30653  
Full text: https://arxiv.org/html/2605.30653v1

### Revision to the claim map

A confidence score should depend on **how agreement was produced**, not only vote share, entropy, or self-reported confidence. Correlation-aware calibration is a promising control component. It does not by itself prove that interaction created unique task-relevant information.

## 2. Emergence and task performance: distinguish structure from capability

Riedl, *Emergent Coordination in Multi-Agent Language Models* (ICLR 2026; arXiv:2510.05174), applies partial-information decomposition to time-delayed mutual information in a group guessing game. Agents receive group-level “too high/too low” feedback but do not directly message each other. Three randomized interventions compare a plain condition, identity/persona differentiation, and an instruction to reason about what other agents might do.

The study reports that personas create more stable identity-linked differentiation, while combining personas with theory-of-mind-like prompting produces stronger goal-directed complementarity. Its regression analysis finds an interaction between synergy and redundancy associated with performance (reported interaction coefficient 0.24, p=0.014). The proposed mediation of the theory-of-mind intervention through synergy is only marginal (ACME 0.034, confidence interval includes zero, p=0.053).

The paper itself limits interpretation: it studies one task, its higher-order measures are constrained to order k=2 in the small-data setting, and the authors state that synergy and redundancy are co-dependent with performance. It also explicitly warns that structural synergy is not evidence of sophisticated cognition or consciousness.

Source: https://arxiv.org/abs/2510.05174  
Full text: https://arxiv.org/html/2510.05174v4

### Interpretation

This is useful support for a **measurable complementarity hypothesis**, not proof that the sum is generally greater than the parts. A structural information measure should be treated as a mediator or diagnostic feature. The primary outcome remains independently verified task utility under intervention.

## 3. Long-horizon benchmark evidence both supports and constrains collaboration

AgentWorld (arXiv:2609.31590; paper record says accepted at COLM 2026) supplies an important counterweight to overly pessimistic readings of multi-agent research. Its tasks are deliberately designed to require 3–20 agents with asymmetric roles and run for 25–55 rounds. On the main set, the strongest primary model, Gemini 3 Flash, reaches 52.0% task success; the single-agent baseline reaches 28.6%; an oracle-communication condition reaches 60.0%. In that sandbox, coordination is materially useful, and better communication still leaves a 40% failure rate.

The same study reports Causal Collaboration Effectiveness (CCE) of 0.320 for Gemini. CCE traces actions backwards from successful outcomes, asking an LLM judge whether earlier actions enabled later contributing actions. In a sample of 84 action judgments, the judge agreed with a human annotator on 69 (82% raw agreement; Cohen’s kappa 0.64). The authors call the inclusion policy intentionally permissive, so CCE is best read as an upper bound on the fraction of useful actions, not a direct causal effect estimate. The small human audit and reliance on an LLM judge remain limitations.

Source: https://arxiv.org/abs/2609.31590

This refines the current synthesis in two directions:
- **Against a blanket anti-MAS conclusion:** a carefully designed, genuinely complementary long-horizon task can show a substantial multi-agent advantage over the tested single-agent baseline.
- **Against a blanket Holobiont conclusion:** the benchmark does not establish unique synergy, superiority to all resource-matched alternatives, or generalization beyond its sandbox. The 52% result is evidence for ordinary multi-agent coordination in that task, not proof of the Treatise’s stronger claims.

A useful follow-up is to compare action-graph attribution with actual interventions: remove, delay, corrupt, or replace a claimed enabling message/action and measure the change in verified outcome. Trace attribution should generate hypotheses; intervention should test them.

## 4. Fault injection: closed-loop recovery beats blind pipeline dependence in tested cases

Jia et al., *MAS-FIRE: Fault Injection and Reliability Evaluation for LLM-Based Multi-Agent Systems* (arXiv:2602.19843, preprint submitted 2026-02-23), defines 15 injectable fault types spanning planning, memory, reasoning, action, configuration, instruction, and communication. It evaluates three representative MAS implementations and separates system-level task survival from fault detection, local correction, and final task recovery.

The authors report that iterative closed-loop designs neutralized over 40% of faults that caused catastrophic collapse in linear workflows. The full text also shows why this must be read conditionally: some injected faults reduce robustness almost to zero in a brittle sequential pipeline, while a critic/refinement loop substantially improves recovery for selected fault classes. Conversely, closed loops do not neutralize every corrupted instruction or trust-policy failure. Some communication anomalies are handled most reliably by deterministic infrastructure rules rather than another model call.

Source: https://arxiv.org/abs/2602.19843  
Full text: https://arxiv.org/html/2602.19843v1

### Architecture implication

Do not encode “immune-like resilience” as a single vague property. Decompose it into:
- detection of a fault,
- local correction,
- containment of propagation,
- recovery of the global task,
- collateral damage and resource cost.

Fault injection is especially important for shared-memory and hypernetwork claims: corrupt a source, remove a specialist, change a schema, or invalidate a dependency, then test recovery against a clean control. A graceful-looking retry is not evidence of restored capability if the final task is still wrong.

## 5. Efficiency mechanisms: useful but not a universal ranking

### MARS: independent review rather than unrestricted round-table debate

Wang et al., *MARS: Toward More Efficient Multi-Agent Collaboration for LLM Reasoning* (arXiv:2509.20502, 2025 preprint), has an author generate an answer, multiple reviewers assess it independently, and a meta-reviewer consolidate feedback. On MMLU, GPQA, and GSM8K, the paper reports approximately 50% lower token use than its multi-agent-debate baseline with broadly comparable accuracy. The result is not dominance on every model/task cell: for example, GPT-3.5 on GSM8K performs worse under MARS than MAD, while some other model/task cells favor MARS.

Source: https://arxiv.org/abs/2509.20502

This supports independent review as an efficiency baseline, not as a universal optimum. It also raises a calibration issue: the paper maps mean token log-probability to a confidence proxy. That proxy should not be assumed calibrated without empirical reliability checks for the relevant model and domain.

### MASBench: protocol, memory, and routing are separable interventions

The public MASBench preprint (arXiv:2610.04672) evaluates protocol, memory, and routing under partial observability. In its reasoning tasks, typed protocols improve scores by 1.5–28.4% across tested backbones while reducing communicated tokens by 45.0–72.7%. In its grid-world task, a gate that first decides whether communication is needed and then selects a recipient outperforms random routing in the reported settings.

Crucially, MASBench defines communication cost as tokens in inter-agent messages and excludes local reasoning tokens. Its communication-efficiency measure therefore is **not total system efficiency**. Results support mechanism-level ablation and targeted routing, but not a claim that the overall system is cheaper unless all relevant resource costs are counted.

Source: https://arxiv.org/abs/2610.04672

## 6. Updated evidence matrix (summary)

| Claim | Evidence from this pass | Status |
|---|---|---|
| Consensus/vote share is a reliable confidence signal | CAGE-Cal finds topology-dependent over- and under-confidence; matched independent runs improve calibration in its tested suite | Naive form contradicted; dependency-aware calibration promising |
| Measurable higher-order synergy proves superior collective capability | ICLR study measures structural synergy in one task; performance relationship is conditional and authors flag endogeneity/task limits | Structural signal supported; general capability claim unproven |
| MAS never beats a single agent | AgentWorld’s designed collaborative tasks show 52.0% vs 28.6% for one model and single-agent baseline | Blanket claim contradicted in this sandbox |
| A MAS advantage establishes Holobiont-specific synergy | AgentWorld is not a test of all strong alternatives or Treatise-specific mechanisms | Unvalidated |
| More interaction necessarily increases utility | CAGE-Cal finds communication-induced regressions; AgentWorld associates excessive chat with poorer results for one model; MASBench supports gated routing | Contradicted as a monotonic rule |
| Fault tolerance follows from adding agents | MAS-FIRE finds architecture- and fault-specific failure/recovery patterns | Unsupported; must test fault class and propagation path |
| Efficient review/topology gains imply universal superiority | MARS/MASBench gains are task/model/configuration dependent; budgets omit some internal costs | Conditional mechanism evidence only |
| Hypernetwork reconstruction, consciousness, immortality | No new direct evidence in this pass | Unvalidated |

## 7. Contradictions and open problems

1. **Counterfactual validity vs. cost:** no-communication counterfactuals clarify communication-induced dependence but require additional runs. The calibration gain must be evaluated at a fixed total budget.
2. **Structural synergy vs. outcome improvement:** PID/TDMI can identify non-additive temporal information, but the mapping from that signal to verified task success remains task- and estimator-dependent.
3. **Action attribution vs. intervention:** CCE is useful for diagnosing wasted effort, but a graph edge inferred by a judge is not itself proof of causal necessity.
4. **Robustness vs. brittleness:** closed-loop review catches some errors; shared context, corrupted instructions, blind trust, or a faulty critic can still cause system-wide failures.
5. **Efficiency metric vs. total cost:** message tokens alone omit private reasoning, prompt/context replay, tools, verifier calls, failed attempts, topology-selection runs, and latency.
6. **Heterogeneity vs. common-mode error:** diverse agents may supply independent evidence, but a shared prompt, tool, memory source, or communication-induced belief can correlate errors.
7. **Generalization vs. benchmark fit:** results from a guessing game, reasoning QA, grid-world, or MMORPG sandbox cannot substitute for held-out task families and different agent/tool stacks.

Priority open questions:
- Can a task-conditioned controller predict the *marginal* value of interaction before spending the interaction budget?
- Does CAGE-style dependency-aware calibration generalize to malicious agents, shared tools, shared retrieval, and temporal memory updates?
- Which intervention-based definition of collective synergy is stable across tasks and budgets?
- How much does an action-graph metric predict the utility loss when the purportedly enabling action is removed or corrupted?
- Can a closed-loop recovery mechanism distinguish a transient tool failure from a semantically corrupted premise?
- How should private reasoning costs be compared when providers expose different token accounting or hide internal reasoning?
- Does the gain survive ownership swaps, randomized agent identity, held-out domains, and stronger single-agent multi-output/ensemble baselines?

## 8. Revised architecture conclusion

The current architecture hypothesis should be **adaptive and evidence-governed, not permanently densely connected**:

1. Start with independent proposals or local observations where diversity and privacy matter.
2. Estimate task need: breadth, complementary private facts, coordination, verification, or persistent-state maintenance.
3. Request/route information only when the expected marginal utility exceeds communication, latency, verification, and privacy costs; hard authorization constraints remain non-negotiable.
4. Track agent/source identity, dependency, communication exposure, version, authority, and time so confidence can account for common-mode errors.
5. Use typed protocols and independent review when they reduce ambiguity; use iterative critique for faults it can actually detect; use deterministic infrastructure for schema, routing, cycle, and access-control failures.
6. Validate critical conclusions against task state or external evidence; use a correlation-aware confidence estimate rather than majority vote alone.
7. Stop, abstain, or revert when further interaction has non-positive expected value or when verification fails.
8. For memory updates and retractions, propagate invalidation to dependent beliefs, summaries, and actions, then re-evaluate downstream claims.

This is a candidate control architecture assembled from separate studies. No cited paper evaluates this entire combination, and no result yet shows that the Cognitive Holobiont is a distinct general intelligence architecture.

## 9. Falsification protocol for the next research stage

### Baselines
Compare: (a) one model with multiple independent samples; (b) single-model multi-output; (c) independent heterogeneous ensemble plus selector; (d) self-consistency; (e) MARS-style independent review; (f) ordinary debate; (g) a structured protocol/memory/routing MAS; (h) governed shared context; (i) topology-aware calibration; and (j) the proposed adaptive controller.

### Randomized interventions
For every task family, randomize agent identity, ownership of decisive facts, communication edge availability, message timing, agent family, source reliability, and fault location. Include no-communication counterfactuals, edge removal, message corruption, delayed updates, stale-memory queries, deletion/access-scope tests, and agent dropout. Use paired seeds where possible and report uncertainty across task instances, not only token-level observations.

### Resource accounting
Charge all observable input/output tokens, local reasoning where available, prompt/context replay, tool calls, verifier calls, retries, independent counterfactual runs, topology-selection runs, wall-clock latency, and monetary cost. If internal reasoning cannot be observed or normalized, label the comparison resource-unmatched and do not claim an efficiency win from message-token counts alone.

### Outcomes
Report separately:
- verified task success and partial progress;
- unique decisive facts recovered;
- diversity and validity of proposals;
- communication-induced regression and improvement;
- calibration (ECE, Brier, discrimination) under topology/domain shift;
- fault detection, local correction, propagation containment, final recovery;
- intervention-validated action contribution;
- drift, wasted actions, and stopping quality;
- privacy leakage and authorization violations;
- stale-action rate and invalidation delay;
- benign-evidence false rejection;
- full resource and latency profile.

### Rejection criteria
Reject the Holobiont-specific synergy claim if its advantage disappears against the strongest feasible resource-matched baseline, is explained by unequal information or extra computation, is not reproduced under ownership swaps and held-out task families, or is measured only by consensus/trace/PID without verified outcome improvement. A general MAS gain is not sufficient; the claimed distinctive mechanism must contribute incremental value under intervention.

## 10. Next priorities

1. Reproduce the CAGE-Cal counterfactual and calibration setup, including the full compute cost of the independent and topology runs.
2. Cross-map its per-agent regression metric with AgentWorld action-attribution and MAS-FIRE fault recovery, while keeping their different constructs separate.
3. Design intervention tests that remove or corrupt purportedly enabling messages/actions.
4. Evaluate adaptive interaction against independent multi-output and review baselines on complementary-information tasks and long-horizon tasks.
5. Extend the claim–evidence matrix and contradiction log before implementation decisions.

The originating Treatise/PDF remains a hypothesis/specification, not established fact.
