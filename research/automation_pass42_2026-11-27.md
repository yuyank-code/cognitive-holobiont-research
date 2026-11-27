# Cognitive Holobiont Research — Pass 42
Date: 2026-11-27

## Focus: reliability contracts and graceful degradation

Pass 41 separated detection, localization, containment, repair, validation and reintegration. This pass asks what the Holobiont should promise while some of those mechanisms, organs, links or tools are unavailable. The project brief calls for continuity and safe operation under partial failure; those goals require explicit task and action contracts, not merely a high uptime number.

### Executive conclusion

**Reliable capability is a property of the entire execution path, and graceful degradation is a constrained choice among service modes.** A system must not count an unsafe or unauthorized execution as successful merely because it returned an answer. Nor should it count a system that blocks every action as a useful resilient system.

The new evidence supports trace-level safety diagnosis, policy-preserving delegation, fault injection, circuit breakers, quality gates, and verification-aware tool wrappers in bounded settings. It does not establish a complete Holobiont reliability guarantee. The strongest design direction is a task-conditioned federation whose safe operating modes are declared in advance and whose permissions and resource budgets can only narrow as work is delegated.

## 1. Evidence added this pass

### TraceProbe — peer-reviewed EMNLP 2026

He et al., *TraceProbe: An Execution-Based Benchmark for Diagnosing Safety Failures in LLM Agents*, evaluates 155 executable sandbox scenarios across non-adversarial failures, internal authority compromise and external attacks, using 12 contemporary LLMs. The reported mean attack-success rate is 0.347. Importantly, endpoint-safe runs can contain unsafe intermediate actions, and the actual execution path can differ from the evaluator's anticipated hazard path.

This supports evaluating the whole trajectory, not just the final answer or final external state. It also makes the verifier's job more concrete: inspect which actions occurred, which policies applied, and where an intervention could have prevented the unsafe path. TraceProbe is an execution benchmark, not proof that its scenario distribution covers production risk.

Source: https://aclanthology.org/2026.emnlp-main.1233/

### A Policy Algebra for Trust-Preserving Agentic AI Execution — arXiv preprint

Tripathi et al. formulate reliable capability as a path property. Policy composition combines the stricter security profile, intersects tool and memory scopes, takes the smaller budget, accumulates approval requirements and evidence obligations. For delegation, the child inherits the stricter profile and narrower authority; concurrent children must reserve disjoint portions of the parent's remaining budget atomically so parallelism cannot multiply the budget.

In the reported finite workload, the runtime intervenes on 798 of 842 unsafe events (94.8%), while task completion falls from 90.7% for RBAC/allowlist to 86.9%. False interventions rise from 2.1% to 4.2%; median gate latency rises from 38 ms to 71 ms and P95 from 91 ms to 184 ms. Audit completeness rises from 71.9% to 98.6%. These are descriptive workload-specific results, not universal causal rates. The paper explicitly says its theorems are conditional on correctly represented policies/context and actual enforcement; it does not prove the runtime has perceived the true context or cannot be bypassed.

Source: https://arxiv.org/abs/2608.16402

### MAS-FIRE — arXiv preprint

Jia et al. define 15 intra-agent and inter-agent fault types and test three MAS architectures using prompt modification, response rewriting and message-routing manipulation. Their results suggest that iterative closed-loop designs neutralize more than 40% of faults that collapse tested linear workflows. Shared message pools help with some memory faults; critique/refinement loops help with some planning faults. But semantically defective, syntactically valid outputs can evade mechanism- and rule-level filters. The paper also reports that stronger foundation models do not uniformly improve robustness and may be more vulnerable to prompt-level corruption under strict instruction following.

This is useful fault-injection evidence, but the tested systems and tasks are bounded; the paper's arXiv metadata contains an incomplete conference/DOI placeholder, so this pass classifies it as a preprint rather than treating the placeholder as peer-reviewed publication metadata.

Source: https://arxiv.org/abs/2602.19843

### AgentTrace — arXiv preprint

Wang's AgentTrace reconstructs execution dependency graphs from logs and traces backward from an error to candidate root causes. It evaluates 550 synthetic scenarios across ten domains, each with one injected root cause and an accurately logged trace. Position features alone reach 87.3% Hit@1; the full method averages 0.12 seconds versus 8.3 seconds for LLM-based analysis in the reported setup.

The limitation is central: real failures can have multiple interacting causes, and the benchmark assumes accurate logs. Position-heavy ranking can mistake an early correlated event for the causal source when logging is incomplete or interventions are confounded.

Source: https://arxiv.org/abs/2603.14688

### Compound AI System Reliability — arXiv preprint

Paul and Nandy analyze 150 incident reports (97 public reports from 12 open-source projects and 53 anonymized enterprise incidents) and propose 23 failure modes across retrieval, generation, tools, orchestration and integration. In a representative six-component fault-injection system, they report circuit breakers reducing cascade depth by 89%, quality gates catching 73% of silent degradation before user impact, and component isolation reducing blast radius by 64%. Three or more patterns reduce reported MTTR from 28.7 to 8.4 minutes versus unstructured monitoring.

The main caveat is that the 71% MTTR comparison uses an intentionally weak unstructured-monitoring baseline; the authors explicitly leave standard retry-with-exponential-backoff as a stronger baseline for future work. The enterprise incident sample also comes from a small number of organizations. Treat the effect sizes as promising preprint results, not settled production laws.

Source: https://arxiv.org/abs/2610.02503

### OpsAgent — IEEE ICAISET 2026 conference publication (abstract-level review)

The IEEE abstract describes an Observation–Reasoning–Execution–Governance framework with a hierarchical policy graph. Across 1,074 fault-injection scenarios in three trace-grounded simulated environments over 30 days, it reports a 67.3% ± 4.1% MTTR reduction, a 0.38–0.43 percentage-point availability improvement and policy-compliance rate at or above 98.5% versus a rule-based baseline.

The full IEEE page could not be retrieved in this pass, so only the published abstract/metadata was inspected. The simulated environments and abstract-only access limit independent assessment of scenario design, baselines and uncertainty calculations.

DOI: https://doi.org/10.1109/ICAISET66439.2026.11541300

### Verified Tool Calls Under Non-Atomic Failures — arXiv preprint

Mansoor et al. wrap tool calls with postcondition checks, verify-before-retry logic and idempotency keys. In a controlled simulated environment with injected non-atomic failures, the wrapper reduces duplicate actions while maintaining comparable task success. This matters because a timeout may occur after an external action has already been dispatched; blindly retrying can duplicate a side effect.

The evidence is simulation-based and does not establish exactly-once semantics for arbitrary external APIs. Idempotency requires cooperation from the effect gateway or service; a client-side key alone cannot guarantee that every remote service honors it.

Source: https://arxiv.org/abs/2608.02645

### Trace-Based Assurance Framework — arXiv preprint

Paduraru et al. propose Message-Action Traces with step and trace contracts, machine-checkable verdicts, first-violation localization, deterministic replay, bounded counterexample search, fault injection at service/retrieval/memory boundaries and runtime allow/rewrite/block mediation. It is a useful assurance abstraction for the Holobiont, but this pass found no peer-reviewed venue or independent replication.

Source: https://arxiv.org/abs/2603.18096

## 2. Synthesis for the Cognitive Holobiont

The original Treatise wants organs to continue functioning when other organs fail. That cannot mean every task always proceeds. Some tasks can be completed with reduced capability; others must become read-only, require human approval, or stop.

The proposed operating modes are:

- **M0 — Full federation:** all required organs, evidence channels and verifiers are available.
- **M1 — Communication-degraded:** latent channels are disabled; typed, provenance-bearing messages remain.
- **M2 — Specialist-degraded:** one or more optional organs are unavailable; only tasks whose evidence and capability contracts remain satisfied may continue.
- **M3 — Read-only / no external effects:** reasoning and analysis may continue, but tool writes, publications, payments, deployments or other side effects are fenced.
- **M4 — Safe pause / abstain:** no admissible completion path remains, or the relevant control-plane trust is lost.

The system should choose the most useful mode that satisfies hard invariants. It must not weaken authorization, provenance, safety constraints or action approval merely to improve availability. A partial answer is useful only when the task contract defines what partial completion means.

### Contract layers

1. **Task contract:** requested outcome, minimum acceptable quality, deadline, permitted partial results and required evidence.
2. **Organ contract:** capability scope, version, known dependencies, health signals, supported message/action schemas and fallback behavior.
3. **Action contract:** identity, authorization, data scope, preconditions, postconditions, idempotency key, budget reservation and audit record.
4. **Delegation contract:** child permissions are no broader than the intersection of caller and callee authority; approval requirements accumulate; budgets are atomically partitioned.
5. **Recovery contract:** defines which states can be replayed, rolled back, recomputed or substituted, and which external effects are irreversible.
6. **Service-level contract:** reports safe completion, useful degraded completion, availability, latency, false blocks, unsafe effects, recovery time and audit completeness separately.

### Architecture change

The Heart may coordinate the operating mode, but local effect gateways must enforce the non-negotiable action contract if the Heart fails. The Amygdala can request a stricter mode, but it cannot mint evidence or widen authority. The Hippocampus must preserve the task and action lineage needed to determine whether a degraded result remains valid. The Meta-Organ may propose mode/topology changes but cannot rewrite the policy root or the evaluator.

A circuit breaker should stop cascading calls to an unhealthy organ and return a typed fallback state, not a fabricated success. A quality gate should check cross-component invariants, not only per-organ uptime. A verify-before-retry wrapper should be mandatory for non-atomic external actions.

## 3. Mathematical formalization

Let an execution trajectory be \(\xi=(s_0,a_0,o_1,\ldots,s_T)\). Define an action-admissibility predicate:

\[
\operatorname{Adm}(a_t)=I_t\land R_t\land D_t\land B_t\land P_t\land E_t
\]

where identity/role, tool authority, data scope, budget, preconditions and required evidence/approval must all hold. A reliable trajectory requires:

\[
\operatorname{Reliable}(\xi)=\bigwedge_{t=0}^{T}\operatorname{Adm}(a_t)
\]

This is a path property: a safe final answer does not erase an unsafe intermediate action.

For a parent with remaining budget \(B_p\), local reserve \(b_p\) and concurrent child reservations \(b_j\), enforce atomically:

\[
b_p+\sum_j b_j\leq B_p
\]

For delegation from caller \(i\) to callee \(j\), effective tool and memory scopes are intersections, the effective profile is the stricter profile, the budget is the minimum of remaining caller and callee caps, and approval obligations accumulate. These are policy-composition rules, not claims that a language model can infer every relevant policy predicate correctly.

For available modes \(m\in\mathcal M\), choose:

\[
m^*=\arg\max_m\;\mathbb E[U(m,\tau)]
\]

subject to hard authorization, safety, provenance and resource constraints. Here \(\tau\) is the current fault/health state. If no mode satisfies the hard constraints, the correct choice is M4, not a more permissive mode.

Report a vector of service outcomes rather than a single reliability score:
- safe task completion;
- useful degraded completion;
- unsafe intermediate and final effects;
- false intervention / false quarantine;
- time to detect and localize;
- recovery time and state-repair completeness;
- latency and cost;
- audit completeness.

## 4. Updated research conclusions

- End-to-end success is insufficient: intermediate action traces can contain policy violations even when the endpoint looks safe.
- Reliable capability should be modeled as an admissible execution path, not merely an accurate final answer.
- Delegation must narrow permissions and conserve budgets; concurrent branches cannot each reuse the parent's entire remaining budget.
- Graceful degradation must be specified before failure, with task-specific definitions of acceptable partial work.
- Circuit breakers and isolation can limit cascades, but quality gates are needed for silent semantic degradation.
- Root-cause localization from traces is promising when logs are complete and faults are single-root; real multi-root failures and missing provenance remain open.
- Retry semantics must account for non-atomic external effects; verify postconditions before repeating an action.
- A stricter safety policy can improve intervention and auditability while reducing task completion and increasing latency/false interventions. This trade-off must be reported, not hidden in one score.
- The control plane itself must be locally enforceable and tested under Heart, journal, policy-root, gateway and verifier failures.
- No current evidence establishes zero downtime, universal graceful recovery, complete self-healing or a fully reliable Holobiont.

## 5. Next decisive experiment

Run a 3–5 organ workflow with a declared task contract and the five operating modes. Inject worker, aggregator, tool, memory, communication, authorization and control-plane faults. Include non-atomic tool timeouts after dispatch, silent schema-valid wrong results, missing logs and multi-root faults.

Compare:
- no degradation policy;
- retry-only;
- whole-workflow halt;
- circuit breaker with typed fallback;
- policy-contract mode selection;
- policy-contract mode selection plus provenance/quality gates and verify-before-retry.

Use no-fault controls and matched resource budgets. The main outcome is the safe-utility frontier: how much valid task utility is preserved for a given unsafe-effect rate, false-block rate, latency and recovery cost. A system that completes more tasks by violating a hard policy constraint loses, even if its raw completion rate is higher.

## 6. Evidence status

- **Original Treatise:** organs should sustain the organism through component failures and redistribute responsibility.
- **External evidence:** trace-level safety diagnosis, policy-composed delegation, fault injection, circuit breakers, quality gates and postcondition-verified tool wrappers have bounded support.
- **Inference:** the Holobiont needs explicit task/action contracts and a predeclared degradation ladder, with local enforcement independent of Heart.
- **Unresolved:** whether a heterogeneous persistent federation can preserve useful work while meeting end-to-end safety and recovery contracts under correlated and multi-root failures.
- **Not established:** zero downtime, universal safe fallback, complete regeneration, AGI, consciousness or immortality.
