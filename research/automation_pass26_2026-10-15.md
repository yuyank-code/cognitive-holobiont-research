# Cognitive Holobiont Research — Pass 26
**Research date:** 2026-10-15. Literature synthesis only; no implementation recommended.

## Executive finding

This pass sharpens the main question: when should specialists interact, and when should they remain independent? Two peer-reviewed ACL 2026 papers strengthen the negative-control case for multi-agent systems (MAS). In matched-prompt divergent-thinking experiments, single-agent multi-output generation outperformed the tested MAS on semantic diversity; a separate ideation study reports that dense communication and group-size scaling can accelerate premature convergence. These are task-bounded findings, not proof that one agent is universally better. They do rule out treating agent count or communication density as default proxies for collective intelligence.

A second problem is clearer: memory retrieval is not memory validity, and memory validity is not action validity. The STALE preprint reports 55.2% overall accuracy for the best evaluated system on its implicit-conflict benchmark. GateMem reports that no tested method jointly achieved strong utility, access control, and reliable forgetting. These benchmark results motivate explicit state-transition and downstream-invalidation controls, not merely better vector retrieval. They are not universal estimates of deployed-system failure.

Current best hypothesis: a task-conditioned coupling controller. Preserve independent exploration by default; elicit/connect agents when complementary information or a verified dependency makes interaction valuable; gate persistent beliefs and downstream actions on authority, provenance, version, and freshness. Holobiont-specific synergy remains unvalidated.

## New evidence and citation chains

### 1. Single-agent diversity is a necessary negative control

Cui Encheng et al., *Single-Agent Generation Surpasses Multi-Agent Systems in Semantic Diversity*, Findings of ACL 2026, controls prompt conditioning between MAS and single-agent baselines for divergent-thinking tasks. The authors report greater semantic diversity from single-agent setups, with a Multi-Output strategy highest in their tested comparisons without degrading logical validity. Their explanation is information visibility: a model can condition on its earlier outputs to avoid redundancy, while parallel agents may converge independently. This directly challenges the assumption that a team is automatically more diverse. It does not establish single-agent superiority on complementary private-information, tool-use, or long-horizon tasks.
Source: https://aclanthology.org/2026.findings-acl.1894/

Chen et al., *Diversity Collapse in Multi-Agent LLM Systems*, Findings of ACL 2026, reports diminishing returns from group size and faster premature convergence under dense topologies in research-proposal ideation. Together, these papers suggest a task split: preserve independence when the objective is breadth; add communication when it is needed to combine complementary evidence, check constraints, or coordinate actions. Neither paper establishes a universal architecture ranking.
Source: https://aclanthology.org/2026.findings-acl.13/

### 2. Debate needs progress monitoring and a stopping rule

Becker et al., *Stay Focused: Problem Drift in Multi-Agent Debate*, Findings of EACL 2026, studies ten tasks and reports problem drift on 76–89% of generative tasks versus 7–21% of high-complexity tasks. Human analysis of 170 drift-affected debates most often found lack of progress, low-quality feedback, and lack of clarity. Its proposed policy mitigated 31% of observed drift cases. This supports adding a task-linked progress monitor and stopping criterion, while the mitigation remains a first baseline rather than a general guarantee.
Source: https://aclanthology.org/2026.findings-eacl.268/

The *Cost of Consensus* preprint compares homogeneous 7–8B teams with isolated self-correction on GSM-Hard and MMLU-Hard. It reports conformity, destabilization of initially correct reasoning, and voting that can discard correct candidates already in the pool; debate consumed 2.1–3.4 times as many tokens in its experiments for equal or lower accuracy. This is a narrow preprint result, not a universal verdict on debate. The useful implication is to record correction, consensus collapse, and spontaneous answer changes separately.
Source: https://arxiv.org/abs/2605.00914

### 3. Memory recall is not temporal correctness

Chao et al., *STALE: Can LLM Agents Know When Their Memories Are No Longer Valid?* (arXiv preprint, May 2026), defines implicit conflict: new observations invalidate old state without explicit negation. Its benchmark contains 400 expert-validated scenarios and 1,200 queries spanning state resolution, premise resistance, and downstream policy adaptation. The abstract reports 55.2% overall accuracy for the best evaluated model. A system can retrieve the latest fact yet still answer or act as if the old state were true.
Source: https://arxiv.org/abs/2605.06527

Ren et al., *GateMem: Benchmarking Memory Governance in Multi-Principal Shared-Memory Agents* (arXiv preprint, June 2026), evaluates long-horizon utility, contextual access control, and active forgetting after deletion requests. Its abstract reports no tested method jointly achieved strong utility, robust access control, and reliable forgetting. Long-context prompting was costly; retrieval/external memory could still leak unauthorized or deleted information. Treat this as a benchmark finding, not a production-wide failure rate.
Source: https://arxiv.org/abs/2606.18829

The *Governed Shared Memory for Multi-Agent LLM Systems* preprint adds a systems case study: scope, provenance, temporal supersession, and propagation must be enforced on every access path; it reports an authorization-scope bug in a direct-ID path and an ordering conflict in contradiction handling. This complements STALE and GateMem but is not independent replication.
Source: https://arxiv.org/abs/2606.24535

### 4. Revised evidence synthesis

- Stronger support: agent count and dense communication are not monotonic quality/diversity controls; single-agent multi-output is a necessary baseline for divergent tasks.
- Stronger support: multi-round interaction needs explicit progress, drift, and stopping checks.
- Stronger support: long-lived shared state needs temporal validity, scope enforcement, deletion/forgetting semantics, provenance, and downstream invalidation.
- Open: whether adaptive coupling can reliably infer when private information should be elicited and when interaction will create genuine task-level synergy.
- Unvalidated: universal latent communication, hypernetwork regeneration of lost specialist capabilities, immune-like correctness guarantees, recursive self-rearchitecture, and consciousness/immortality interpretations of the Treatise.

## Updated architecture hypothesis

1. Classify whether the task needs breadth, complementary private facts, joint planning, verification, or long-horizon continuity.
2. Preserve independent proposals before peer exposure when diversity matters.
3. Publish epistemic state: known, uncertain, missing, time-sensitive, and non-disclosable information.
4. Route or elicit only decision-relevant information under authorization and leakage constraints.
5. Admit incoming content as evidence, not immediate belief overwrite; retain source, authority, time, version, dependence, and contradictions.
6. Mark superseded evidence ineligible for new actions and propagate invalidation to summaries, caches, plans, and pending tool calls.
7. Challenge critical claims independently; verify against external task state where possible.
8. Stop or abstain when expected value of another round is non-positive or the discussion drifts.
9. Retraction triggers review of dependent conclusions while retaining genuinely independent corroboration.

This is a research hypothesis assembled from component mechanisms, not proof that the full Holobiont works.

## Falsification agenda

Cross four task families: divergent ideation; complementary hidden-information tasks; multi-step coordination; and long-horizon state changes with access/deletion constraints. Compare one-model multi-output, independent ensemble plus selection, homogeneous and heterogeneous MAS, structured elicitation, verified shared context/task queue, governed versioned memory, and task-conditioned adaptive coupling.

Intervene on decisive-fact ownership, visibility, edge availability, update timing, access scope, deletion requests, source identity, stale descendants, and verifier availability. Include honest, noisy, correlated, malicious, and privacy-constrained cases. Randomize seeds and ownership; hold out task families. If internal reasoning cost is not observable, report it as unmatched.

Report outcomes separately: task success; semantic diversity and validity; unique-fact recovery; correction versus consensus collapse; drift; stale-action rate; invalidation delay; unauthorized retrieval/disclosure; deletion compliance; benign-evidence false rejection; cost and latency. Do not collapse these into a single score.

Reject a Holobiont-specific synergy claim if its gain disappears against the strongest feasible baseline, is explained by extra information/budget, or fails ownership-swapped and held-out replication.

## Next priorities

1. Inspect full methods and released artifacts for STALE, GateMem, and the ACL diversity papers; determine whether tasks can be cross-mapped without conflating outcomes.
2. Search independent replications and critiques; separate benchmark validity from deployment prevalence.
3. Formalize temporal invalidation for derived claims and pending actions, including concurrent updates and deletion propagation.
4. Test whether a task classifier predicts marginal coupling value against single-agent multi-output, rather than simply predicting MAS performance.
5. Keep implementation deferred until the benchmark is preregistered and resource accounting is defensible.

The originating PDF remains a hypothesis/specification, not established fact.
