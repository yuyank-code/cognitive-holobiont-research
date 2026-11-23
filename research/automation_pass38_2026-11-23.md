# Cognitive Holobiont Research — Pass 38
**Date:** 2026-11-23  
**Focus:** Effective organ independence, response diversity, and common-mode failure.

## Executive conclusion

The original Treatise wants autonomous, heterogeneous organs that can preserve system function when one component fails. This pass asks a narrower engineering question:

**When do two organs count as genuinely independent sources of protection or evidence, rather than two interfaces that repeat the same blind spot?**

New evidence strengthens a critical design rule:

**Do not count organs. Measure the task- and failure-specific dependence of their errors, and separately measure the unique capability each organ contributes.**

A single scalar “diversity” score is inadequate. The Holobiont needs at least two distinct quantities:
1. **Functional complementarity:** does an organ contribute a capability, observation, or evidence item unavailable from the current coalition?
2. **Response diversity:** when multiple organs perform overlapping protective functions, do they fail differently under the same task and perturbation?

A specialist population should contain both complementary roles and strategically redundant, differently responding backups. These are different design objectives and should not be collapsed into a single diversity maximization objective.

## 1. Project-specific question

The Treatise's immune system, distributed organs and regeneration mechanism assume that surviving components can compensate for a failed or compromised organ. That assumption only works if the remaining components are not all vulnerable to the same cause.

The relevant common-mode dependencies include:
- shared base weights, architecture, tokenizer, pretraining corpus, distillation teacher or alignment process;
- common system prompts, role templates, policy/evaluator models or reward models;
- shared memory stores, retrieval indices, latent codecs, bridges, hypernetworks or training pipelines;
- common tools, APIs, data sources, credentials, network providers and orchestration code;
- shared task decomposition, stopping rules, or the same unverified evidence copied between organs.

Provider diversity is therefore a prior signal, not proof of independence. Conversely, two models from one provider are not automatically identical in their failure behavior. Independence must be measured on the function and failure modes the system intends to tolerate.

## 2. New evidence

### 2.1 Correlation limits the reliability of ensemble decision making — Discover Informatics, 4 November 2026

Morante and Romero García-Rubio give an explicit variance-based effective-voter model. For N equally competent agents with common pairwise correctness correlation rho:

N_eff = N / (1 + (N - 1) rho)

This is an effective sample size for the variance of the average correctness vote under exchangeability, equal competence and common correlation—not a universal measure of information, intelligence, or capability.

Their small MMLU proof-of-concept used 562 four-option questions:
- five temperature samples from one model: rho = 0.85, N_eff ≈ 1.1;
- five personas of one model: rho = 0.85, N_eff ≈ 1.1;
- five models from different developers: rho = 0.38, N_eff ≈ 2.0.

The different-developer plurality reached 0.923 accuracy, but remained below its best member at 0.940. Equal-weight voting therefore wasted some of the best model's advantage. The experiment is intentionally small: one benchmark, one base model for the cosmetic-diversity conditions, five models in the cross-family condition, and single-letter answers. The article explicitly says correlation varies by task and that its main theory assumes exchangeable agents.

Source: https://doi.org/10.1007/s44564-026-00040-z

### 2.2 Inferred Generative-Process Diversity Predicts Correlated Failure — arXiv preprint, 3 September 2026

Tieman and Markou study 38 models, 100 open-ended prompts and ten disjoint benchmark families. They estimate an output-derived “inferred generative-process diversity” using normalized compression distance (NCD) after a byte-permutation control. Their cross-controlled partial rank association with correlated wrong-answer agreement is -0.216, with a 95% interval of [-0.309, -0.122], and the direction is negative on all ten benchmark families.

This is useful because semantic similarity alone may miss response regularities that predict shared errors. But the measure does not recover a model's internal algorithm. The authors explicitly say it is not a true metric and is compressor-dependent. Their initial experiment studies base-model input/output behavior without agent scaffolding, tools or shared memory. The result is predictive and associational, not a causal demonstration that increasing NCD will improve a Holobiont.

Source: https://arxiv.org/abs/2609.03422

### 2.3 Are Diversity Metrics Measuring Diversity? — arXiv preprint, 22 July 2026

Donghwan Kim audits 31,900 model subsets from 30 models on MMLU-Pro, with a 29-model TruthfulQA replication, under explicit capability controls.

Reported results:
- simple majority voting beats the strongest member in 9.98% of canonical size-three subsets;
- held-out best-member selection raises that to 18.71%;
- the pooled size-two-to-four rate is 1.27%, partly affected by deterministic even-size tie behavior;
- after capability control, most raw diversity associations attenuate, reverse or become specification-dependent;
- pairwise co-failure is the most directionally stable residual association, but its magnitude is configuration-dependent and its held-out prediction of rare positive-gain events is weak (AUC 0.597).

The paper is a measurement audit of majority voting, not a test of learned selectors, private-evidence collaboration, parallel tool use, or fault recovery. It warns that apparent diversity measures can mostly re-express member capability.

Source: https://arxiv.org/abs/2607.20768

### 2.4 D-FUSEr — ICML 2026, PMLR 306

Baek et al. show that aggregation depends on the distribution of errors, not only single-sample accuracy. Their diverse-failure reward and “anti-vote” mechanism explicitly model common mistakes. Across three model families and four benchmarks, they report improvements to majority vote and iterative refinement without reducing single-sample accuracy in their tested settings.

This is an intervention-oriented complement to passive diversity measurement. It does not justify deliberately making safety-critical organs unreliable; it motivates training and selection objectives that reduce predictable common-mode errors while preserving individual competence.

Source: https://proceedings.mlr.press/v306/baek26a.html

### 2.5 Correlated Errors in Large Language Models — ICML 2025

Kim et al. evaluate more than 350 LLMs across leaderboard and resume-screening settings. They find substantial correlated errors, including shared wrong answers, and report that provider, architecture and training lineage influence correlation. More capable models can still share errors even when their architectures and providers differ.

This establishes that model/vendor diversity alone is not a sufficient independence guarantee.

Source: https://proceedings.mlr.press/v267/kim25e.html

### 2.6 HiddenBench — ICML 2026

Li, Naito and Shirado's 65-task HiddenBench separates individual reasoning from collective reasoning over private information. Across 15 frontier models, distributed-information multi-agent performance is 30.1%, compared with 80.7% for a single agent given the complete information. The authors identify a failure to recognize latent information asymmetry: agents converge on expressed shared evidence instead of asking what others know but have not yet revealed.

This is a different failure from correlated voting. A group can contain distinct private facts and still fail to exploit them. The Holobiont therefore needs both response-diverse redundancy and active elicitation of complementary information.

Source: https://proceedings.mlr.press/v306/li26ej.html

### 2.7 Self-Anchored Consensus — 2026 preprint

The SAC work uses receiver-side evaluation, bounded filtering and (F+1)-robust graph conditions to reduce the influence of Byzantine neighbors. Its experiments use small seven- or nine-agent networks and focused tasks. The stated guarantees concern retaining and propagating reliable information under explicit fault and graph assumptions; they do not guarantee truth. A receiver can itself be wrong, and evaluator calls add cost.

Source: https://arxiv.org/abs/2605.09076

## 3. Revised architecture conclusion

The Holobiont should not maximize a single global diversity score. It should maintain a **Resilience-Aware Organ Population** with three layers of description:

1. **Capability map:** which tasks, modalities and evidence sources each organ can handle; measure unique contribution through ablation, ownership swaps and conditional utility.
2. **Failure-dependence map:** which organs fail together under each task family and perturbation; measure pairwise and higher-order co-failure, including shared dependency ancestry.
3. **Dependency/provenance graph:** record shared weights, training lineage where known, evaluator, memory, codec, tools, data sources, credentials and infrastructure.

For overlapping critical functions, choose backup organs with different failure responses. For complementary specialist roles, choose organs that add distinct capabilities and information. Do not penalize a specialist merely because its error correlation with an unrelated specialist is undefined or irrelevant.

The immune layer should estimate dependence per domain and per failure mode, preserve minority evidence, and avoid majority-vote truth claims. The repair layer should be tested against common-mode compromise of the repair generator, shared codec, memory and training source.

## 4. Mathematical formalization

For task domain d and perturbation/failure mode f, let X_i^(d,f) be organ i's binary correctness indicator. Let R^(d,f) be the correlation matrix of those indicators over a representative evaluation set.

For equal-weight, equal-variance agents:

N_eff^(d,f) = N^2 / (1^T R^(d,f) 1)

Under exchangeable pairwise correlation rho this reduces to:

N_eff = N / (1 + (N - 1) rho)

For normalized weights w and standardized equal-variance correctness variables, the variance-equivalent effective size is:

N_eff(w) = 1 / (w^T R w)

These are variance-based diagnostics. They do not measure unique information, task coverage, capability, truth, or robustness outside the sampled task/perturbation distribution. With unequal competences, report the full covariance/correlation matrix and a clearly defined weighted reference variance rather than forcing a single scalar.

For complementary evidence, estimate organ i's marginal contribution to coalition S:

DeltaU_i(S) = U(S union {i}) - U(S)

Measure this with randomized organ ablations, evidence ownership swaps and held-out external scoring. Where probabilistic labels are available, conditional mutual information I(Y; E_i | E_S) can be a secondary diagnostic, but information is not automatically usable or safe.

## 5. Decisive experiments

1. **Same-model clones vs prompt variants vs different families vs independently trained specialists.** Measure accuracy, calibration, pairwise error correlation, same-wrong-answer agreement and effective size.
2. **Capability-controlled selection.** Compare raw diversity, NCD/IGP, CAPA-like error overlap and co-failure metrics after controlling for individual capability and capability gap.
3. **Role-specific redundancy.** Build multiple organs for one critical function and inject identical perturbations; test whether response diversity predicts graceful degradation.
4. **Complementary-specialist test.** Give organs private evidence and swap evidence ownership while keeping weights fixed; measure conditional contribution and successful elicitation.
5. **Common-mode dependency injection.** Corrupt shared prompt, evaluator, memory index, codec, hypernetwork, data source, toolchain and orchestration separately and jointly.
6. **Repair under common-mode compromise.** Remove an organ and corrupt one shared repair dependency; compare surviving-organ reconstruction with checkpoint, distilled backup, retraining and external specialist replacement.
7. **Longitudinal homogenization.** Jointly train or repeatedly debate specialists; measure whether their error covariance, capability profiles and response diversity collapse over time.

## 6. What would falsify the distinctive claim?

The resilience claim weakens or fails if:
- vendor/model-family differences do not predict lower co-failure after capability control;
- measured response diversity does not predict improved failure tolerance on held-out perturbations;
- a single model with equal compute and information plus best-of-K or self-conditioning matches the federation;
- organ ablation shows no unique contribution after accounting for extra calls and evidence;
- topology or training causes error correlations to rise until redundancy is nominal only;
- shared evaluator, codec, memory or repair-generator compromise defeats the network as easily as a single-model baseline;
- the population cannot maintain role-specific capability and response diversity over time.

## 7. Research status

This pass adds a measurable distinction between *functional complementarity* and *response diversity*. The former is needed to combine private expertise; the latter is needed for redundancy. A population can have one without the other.

The strongest next milestone is an organ-independence audit followed by common-mode fault injection. It should precede any claim that the Holobiont's immune system, redundancy or regeneration is resilient.

No implementation, universal ensemble superiority, independent-organ guarantee, full regeneration, AGI, consciousness or immortality is established by this evidence.
