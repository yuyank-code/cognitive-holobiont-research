# Cognitive Holobiont Research — Pass 33
**Date:** 2026-11-18  
**Focus:** Capability regeneration, localized model repair, Byzantine-resilient collaboration, and recoverable self-modification.

## Executive finding

This pass investigates the most ambitious and failure-sensitive part of the originating Treatise: whether surviving organs can repair or regenerate a failed specialist, and whether a distributed network can continue making reliable decisions when some organs are compromised.

The evidence now supports a more precise, three-level distinction:

1. **Localized repair of a known damaged model component:** supported in bounded settings. New 2026 studies repair neurons/layers using fault localization, clean reference behavior, task data, and explicit repair objectives.
2. **Recovery of forgotten capabilities in an existing adapted model:** promising but early. A new October 2026 preprint uses a hypernetwork to generate small repair side-nets for LoRA-fine-tuned LLMs, recovering some general performance while preserving specialization.
3. **Regeneration of a missing independent specialist from other surviving organs, without access to its checkpoint, teacher, or unique training data:** still un demonstrated. None of the new work establishes this strongest Holobiont claim.

On fault tolerance, the strongest new result is a peer-reviewed EMNLP 2026 paper introducing decentralized receiver-side filtering and graph robustness conditions for LLM agents under a bounded Byzantine threat model. It improves the evidence base for an immune/fault-containment layer, but it does not make consensus equivalent to truth: the evaluator can itself be wrong, the graph assumptions matter, and the tested setting is small and single-turn.

A further design correction comes from self-modification research: a change that improves current capability can still be impossible to safely undo later. Recoverability must therefore be an admission condition for persistent architectural mutations, not merely a rollback feature added after failure.

**Architecture consequence:** treat regeneration as a measured recovery pipeline with explicit retained-information inventories, trusted references, validation gates, and rollback semantics. Do not encode “every organ can regenerate every other organ” as an assumed property.

---

## 1. Which part of the Holobiont is under investigation, and why

The Treatise proposes Hyper-Network DNA distributed across organs, shadow copies, immune detection, and self-healing while the system continues operating. Its core ambition is stronger than conventional checkpoint recovery: remaining organs should retain enough shared structure and knowledge to recreate a missing organ's useful capability.

This claim matters because it determines whether the Holobiont is merely:
- a modular multi-model application with redundancy;
- a system that can patch a damaged component when a healthy reference remains; or
- a genuinely regenerative architecture whose surviving components can reconstruct a lost capability without relying on an external backup.

Those are different scientific claims and need separate experiments.

This pass also examines the immune layer because any regeneration mechanism is unsafe if a malicious or corrupted organ can poison the repair generator, supply false training targets, or manipulate the reintegration test.

---

## 2. New evidence: model repair and capability recovery

### 2.1 HyperRepair — generated repair modules for forgotten LLM capabilities

**Source/status:** Tang et al., “HyperRepair: Recovering Forgotten General Capabilities of Fine-Tuned Language Models,” arXiv preprint posted 30 October 2026. Not treated as peer-reviewed evidence in this pass.

The method trains a hypernetwork on repair examples from source LoRA-adapted models. It uses activation fingerprints to generate a model-specific Repairing Side Net (RSN), then applies a prompt-conditioned gate so the repair is active only when appropriate. The paper evaluates Qwen2.5-7B and Llama-3.1-8B, across 12 adaptation domains and 15 general benchmarks. On its default split, it reports recovery to 93.4% of the base model's average general score while retaining 99.5% of the fine-tuned model's average domain score.

Why it matters:
- It is directly relevant to the Treatise's idea that a generator can produce task-specific repair structures.
- It shows that a generated repair module can recover some general behavior lost during specialization without retraining the target model on its original adaptation domain.
- It supports selective repair rather than always-on correction: the paper's ablation reports that always activating the repair can reduce domain performance.

Critical boundary:
- This is not reconstruction of a deleted specialist. The base model and its fine-tuned LoRA model still exist.
- The generated object is a relatively small side network (about 0.13% of the backbone parameter count), not a full replacement 7B/8B specialist.
- HyperRepair trains separate generators for the two backbone families; the result does not show one generator recovering arbitrary heterogeneous models from one another.
- Its “unseen domain” test is a held-out adaptation domain within the studied backbone setup, not a completely unseen architecture or modality.
- It is a preprint, so independent replication and broader evaluation are still needed.

**Interpretation:** evidence for *repairing forgotten capabilities in an extant model*, not for organ resurrection.

### 2.2 Universal Hypernetworks for Arbitrary Models — broader parameter generation, but not yet large-model regeneration

**Source/status:** Zhou, “Universal Hypernetworks for Arbitrary Models,” arXiv preprint posted 2 April 2026.

This work proposes a fixed-architecture generator that predicts target-network weights from deterministic parameter-index, architecture, and task descriptors. It evaluates vision, graph, text-classification, and formula-regression tasks, and reports multi-model, multi-task, and recursive generation experiments. The recursive experiment reaches three intermediate generated hypernetwork levels on an MNIST MLP, with accuracy declining as recursion depth increases.

Why it matters:
- It makes the “Hyper-Network DNA” idea more concrete: one generator can condition on model structure and task, rather than requiring a separate output head for every target architecture.
- It suggests that reusable parameter-generation structure can span multiple small model families.
- It gives a testable path for generating specialist initializations or adapters from descriptors.

Critical boundary:
- It is an arXiv preprint by a single author, not peer-reviewed evidence in this pass.
- The experiments are small compared with modern foundation-model organs; they were run on a single RTX 4090.
- The authors explicitly report that UHN does not consistently match direct training on all tasks, does not generate some non-trainable state such as BatchNorm running statistics, and adds training compute and memory overhead.
- The multi-task experiments show cross-task interference; the recursive result is limited to the tested MNIST MLP setup and three generated levels.
- It does not test deleting one independently trained specialist and recovering it from other specialists' knowledge.

**Interpretation:** a promising parameter-generation primitive, not evidence for universal distributed regeneration.

### 2.3 Self-healing neural networks — local patching when a clean reference exists

**Source/status:** Reddy et al., “Self-healing neural networks via modular patch layers for diverse structural and adversarial damages,” *Scientific Reports*, published 22 June 2026; open access.

The method detects an affected layer using activation discrepancies and trains a small patch module to approximate the clean layer's transformation. The reported experiments cover MNIST, Fashion-MNIST, Sign Language MNIST, and CIFAR-10. On the MLP structural-damage tests, the patch brings performance close to the original baseline. On the CIFAR-10 CNN, however, the reported classifier-head repair improves accuracy from 12.9% after damage to 34.9%, still below the 61.6% baseline.

Critical boundary:
- The patch is trained using activations from the pre-damage healthy model as targets. This is a teacher/reference signal.
- The main evidence is on relatively small networks and controlled layer corruption.
- The paper itself notes that multi-layer effects and deeper CNNs reduce recovery effectiveness, and that transformer validation remains future work.
- It repairs a damaged layer's mapping; it does not regenerate a whole independent model from peer organs.

**Interpretation:** useful precedent for localized fault isolation and repair, but it depends on information that the strongest Holobiont regeneration claim would need to preserve or reconstruct.

### 2.4 NSRepair — fault localization and multi-objective repair

**Source/status:** Du et al., “Neural Network Repair With Shapley-Guided Search,” *CAAI Transactions on Intelligence Technology*, first published 11 May 2026; open access, with code linked through Zenodo.

NSRepair uses Shapley-value-based neuron localization and multi-objective optimization to balance defect reduction against preservation of the model's other behavior. It tests four repair objectives: local robustness, fairness, backdoor removal, and safety, across LeNet-style, ResNet, VGG, and small MLP models. This gives the Holobiont a useful design lesson: repair should optimize both the targeted defect and the preservation of unaffected capabilities.

Critical boundary:
- The authors report that Shapley estimation becomes prohibitively expensive beyond roughly 100M parameters.
- The current study handles one defect objective at a time; simultaneous conflicting defects remain open.
- Its static property metrics do not solve long-horizon sequential decision repair.
- It is still component-level repair, not regeneration from peer organs.

**Interpretation:** the immune layer should not only label an organ “bad”; it should localize the failure and quantify the trade-off between repair and collateral capability loss.

---

## 3. New evidence: fault containment in communicating agents

### 3.1 Self-Anchored Consensus (SAC) — peer-reviewed EMNLP 2026

**Source/status:** Lee, Yun, Panagou, and Karimireddy, “Robust Multi-Agent LLMs under Byzantine Faults,” *Proceedings of EMNLP 2026*, pages 44639–44657, DOI 10.18653/2026.emnlp-main.1960.

SAC is a decentralized filter-and-refine protocol. Each receiver independently scores incoming peer responses using its own model, filters the lowest-scoring messages under a local Byzantine bound, and refines its own answer using the remaining responses. The paper derives graph robustness conditions based on (F+1)-robustness and evaluates networks of seven and nine agents.

Why it matters:
- It rejects trust based only on the sender's self-reported confidence.
- It makes communication topology a formal part of the fault-tolerance design.
- It reports that SAC preserves stronger agents while often improving weaker-but-honest agents, whereas confidence-weighted baselines can be manipulated by falsified confidence.
- It gives the Holobiont an implementable candidate for one narrow immune function: local message filtering without a single central judge.

Critical boundary:
- The formal setup assumes an F-local Byzantine model and a static undirected communication graph.
- The benchmark tasks have objectively verifiable answers; this does not directly cover open-ended scientific reasoning, subjective decisions, or ambiguous real-world perception.
- The tested networks are small (n=7 or 9), and the adversarial behavior is focused; the authors list dynamic graphs, multi-turn reasoning, and tool use as outside the current evaluation.
- Receivers still use their own LLM as the evaluator. An evaluator that is wrong or overconfident can discard a correct minority response.
- Stronger graph robustness requires denser communication and higher inference/communication cost. The paper reports n(1+2T) model calls for n agents and T rounds.

**Interpretation:** fault containment is more credible when receivers independently inspect evidence and topology is designed for resilience. It still does not prove that a consensus answer is true.

### 3.2 CP-WBFT — peer-reviewed AAAI 2026, with a caution about confidence

**Source/status:** Zheng et al., “Rethinking the Reliability of Multi-agent System: A Perspective from Byzantine Fault Tolerance,” AAAI-26, published 14 March 2026.

The paper proposes confidence-probe-based weighted Byzantine consensus and reports results under extreme simulated fault rates, including a 6-of-7 Byzantine setting. However, the SAC paper identifies a key weakness in this line of approach: if agents can falsify their self-reported confidence, confidence weighting becomes a vulnerability. SAC replaces sender-reported trust with receiver-side scoring.

The extreme fault-rate headline should not be generalized into a claim that LLM networks defeat classical Byzantine limits. The experiments use small curated benchmark sets and task/topology-specific assumptions. “High accuracy at 6 of 7 malicious nodes” is not a general guarantee for arbitrary agents, arbitrary tasks, or adaptive adversaries.

**Interpretation:** use the paper as evidence that LLM agents can sometimes inspect message content rather than follow simple majority behavior, but do not treat self-confidence as a secure trust signal.

### 3.3 MAS-FIRE — fault injection is necessary, not optional

**Source/status:** Jia et al., “MAS-FIRE: Fault Injection and Reliability Evaluation for LLM-Based Multi-Agent Systems,” arXiv preprint posted 23 February 2026. The arXiv record reviewed here is treated as a preprint.

MAS-FIRE defines 15 fault types across agent cognition and coordination, injected through prompt modification, response rewriting, and message-routing manipulation. It studies three representative architectures and reports that iterative closed-loop designs neutralize over 40% of faults that cause catastrophic collapse in linear workflows. It also finds that stronger foundation models do not uniformly improve robustness; strict instruction following can make some prompt-corruption failures worse.

**Interpretation:** the Holobiont needs process-level fault injection and traces, not only end-task accuracy. A system can fail semantically without raising a software exception.

---

## 4. New evidence: self-modification must be recoverable

### EvoUndo — recoverability-constrained self-evolution

**Source/status:** Sah et al., “EvoUndo: Recoverability-Constrained Self-Evolution for LLM Agent Harnesses,” arXiv preprint posted 28 August 2026.

EvoUndo studies agents that modify prompts, tools, middleware, resources, and runtime harness state. Its central finding is that a mutation that improves current capability may still be unsafe to keep if its effects cannot later be reversed in changed or concurrent states. On 600 unseen self-evolution tasks, the authors identify 197 capability-positive mutations that fail their recovery verification under the original recovery representation. Their richer recovery calculus recovers many of these, but results depend on state-address grounding and recovery-language expressivity.

An especially useful comparison: when the exact affected pre-state is known and serializable, effect-scoped snapshots outperform the synthesized recovery approach in the reported selective-recovery tasks. The paper therefore does not argue that generated rollback should replace ordinary transactions.

**Holobiont design consequence:**
- Persistent changes to organs, bridges, routing, memory schemas, or constitutional policy should be treated as transactions.
- Record exact state addresses, pre-change snapshots or write-ahead logs, dependency versions, and recovery witnesses.
- Test rollback on counterfactual states, not only the nominal state in which the change was created.
- A mutation should not be admitted merely because it improves a benchmark; it must also satisfy a recovery contract and security review.
- Prefer snapshots/WAL when the affected state is precisely known and cheaply restorable; use synthesized recovery only where inverse semantics are genuinely unavailable.

This changes the Meta-Organ design: **recoverability is an invariant of self-modification, not an optional repair feature.**

---

## 5. Updated claim-evidence assessment

| Holobiont claim | Evidence after Pass 33 | Status |
|---|---|---|
| A damaged model component can be localized and patched | SHNN and NSRepair show bounded localized repair using references, data and explicit objectives | Supported in narrow settings |
| A generator can recover some lost capabilities in an extant adapted LLM | HyperRepair reports held-out-domain general-capability recovery with a generated side-net | Promising preprint; not independent-organ regeneration |
| A reusable hypernetwork can generate different model families | UHN reports small-scale vision, graph, text and formula models plus recursive generation | Promising preprint; scale and performance gaps remain |
| A missing specialist can be regenerated from surviving organs alone | No new source directly demonstrates this exact setting | Unvalidated; decisive gap remains |
| Decentralized filtering can reduce Byzantine influence | SAC has peer-reviewed EMNLP evidence under a bounded graph/threat model | Supported conditionally |
| Confidence-weighted majority is robust | CP-WBFT results are task-specific; falsified sender confidence is a vulnerability | Not a safe default |
| Closed-loop topology can improve fault recovery over linear workflows | MAS-FIRE reports this under injected faults | Promising preprint; needs replication and matched-cost study |
| A self-modifying agent can always undo its changes | EvoUndo finds many capability-positive mutations are not recoverable under limited recovery representations | Rejected |
| A recoverability gate should precede persistent self-modification | EvoUndo supports recovery verification and counterfactual testing; snapshots/WAL remain preferable when available | Strong design recommendation, not a complete formal guarantee |
| Holobiont-specific regeneration beats best backup/retrain baseline | No matched-budget experiment yet | Unvalidated |

---

## 6. Mathematical formalization added this pass

### 6.1 Separate exact-weight reconstruction from functional recovery

Let the lost specialist be O_j and the reconstructed candidate be O_hat_j.

Do not use parameter distance alone as the recovery score. Neural networks can represent similar functions with different parameterizations. Evaluate:

\[
D_{\mathrm{func}}(O_j,\hat O_j)
=\mathbb{E}_{x\sim\mathcal D_{\mathrm{heldout}}}
[d(O_j(x),\hat O_j(x))].
\]

For task utility:

\[
\Delta U_{\mathrm{recover}}
=U(\hat O_j;\mathcal D_{\mathrm{heldout}})
-U(O_{\mathrm{fallback}};\mathcal D_{\mathrm{heldout}})
-C_{\mathrm{recovery}}.
\]

Report exact-weight recovery separately where the architecture and parameter alignment make it meaningful. Report functional equivalence, calibration, robustness, latency and energy separately.

### 6.2 Information retained after loss

Let K_j denote the task-relevant capability information of the original organ, and Z_survive denote all information accessible after its deletion: surviving model states, memories, adapters, logs, shared generators, training data and provenance.

The recovery ceiling depends on what information remains:

\[
\mathcal R^*(Z_{\mathrm{survive}})
=\sup_{\hat O\in\mathcal A(Z_{\mathrm{survive}})}
\mathbb E[U(\hat O)].
\]

If the surviving state contains no information that distinguishes the target capability from the prior possibilities, recovery cannot exceed what can be inferred from the task prior and any external data. This must be tested by controlled removal of each information channel; it is not enough to hide the checkpoint while leaving a distilled teacher or duplicate training set accessible.

### 6.3 Repair must preserve unaffected behavior

For target defect objective L_defect and preservation objective L_preserve:

\[
\min_{\theta_{\mathrm{repair}}}
\left(
L_{\mathrm{defect}}(\theta_{\mathrm{repair}}),
L_{\mathrm{preserve}}(\theta_{\mathrm{repair}})
\right)
\]

subject to hard safety, privacy, provenance and authorization constraints. Report the Pareto frontier instead of hiding trade-offs inside one arbitrary scalar score.

### 6.4 Recoverability as a mutation-admission condition

Let s be the current system state and m a proposed persistent mutation. Admit m only if:

\[
\operatorname{Improve}(m,s)\geq \tau_U
\quad\land\quad
\operatorname{Recoverable}(m,\mathcal S_{\mathrm{counterfactual}})\geq \tau_R
\quad\land\quad
\operatorname{Safe}(m)=1.
\]

The recovery test must include concurrent updates, changed dependencies, partial failure, and a mutation that succeeds initially but later becomes obsolete. Store the recovery witness and pre-state needed to restore observational equivalence.

### 6.5 Byzantine containment is not correctness proof

Let each receiver i evaluate message m_j using local evaluator phi_i. A filter can limit the influence of messages scored below a threshold or below the receiver's own answer. This can protect against some Byzantine senders only under explicit assumptions about the number and placement of faulty neighbors, graph robustness, and evaluator competence.

Therefore measure both:
- false acceptance of harmful or misleading messages;
- false rejection of correct minority evidence.

A robust network should minimize both, not maximize agreement.

---

## 7. Contradictions and negative results sharpened

1. **Repair with a teacher vs regeneration without a teacher:** SHNN's patch target comes from the clean pre-damage model. It cannot be cited as proof that peers can recreate a lost model when no teacher remains.
2. **Capability restoration vs full specialist reconstruction:** HyperRepair restores some general behavior in an extant model by adding a small side network. It does not reproduce the missing model's complete weights or all its capabilities.
3. **Architecture-agnostic generator vs scale:** UHN's cross-architecture results are promising, but its own limitations include direct-training performance gaps, missing non-trainable state, compute overhead, and small-model evaluation.
4. **Confidence vs trust:** CP-WBFT's sender confidence can be falsified. Receiver-side scoring in SAC is safer against this attack, but receiver models can still be wrong.
5. **Formal robustness vs empirical correctness:** SAC's graph conditions preserve useful information under its model; they do not certify truth in open-ended tasks.
6. **Fault tolerance vs cost:** more robust graph connectivity increases communication and inference costs.
7. **Improvement vs reversibility:** a mutation can improve forward task utility while destroying the information needed to reverse it.
8. **Generated rollback vs ordinary transactions:** EvoUndo's own results show effect-scoped snapshots are superior when the exact affected pre-state is available.
9. **Local patching vs distributed recovery:** repair of one known layer is a much easier problem than recovering a missing organ with no clean reference.
10. **One defect vs interacting defects:** NSRepair's current experiments target one property at a time; the immune system must eventually handle simultaneous, conflicting defects.

---

## 8. Architecture update

The most defensible architecture after this pass has five distinct planes:

1. **Specialist plane:** heterogeneous organs retain local capability, independent evaluation and private evidence.
2. **Communication/coordination plane:** explicit provenance-bearing messages, selective latent bridges only where causal transfer is demonstrated, and receiver-side filtering rather than sender self-confidence.
3. **Integrity plane:** fault localization, dependency tracking, fault injection, quarantine, audit trails and false-positive/false-negative monitoring.
4. **Repair plane:** localized patching, capability recovery modules, hypernetwork-generated adapters or replacement candidates, with explicit information-source accounting.
5. **Mutation-control plane:** transactional state capture, sandboxed changes, counterfactual rollback tests, independent validation and gated reintegration.

Do not let the repair generator share unrestricted write access to all organs or their trust roots. A compromised generator or shared latent codec could become a common-mode failure affecting every organ.

### Proposed recovery states

- Healthy
- Suspected fault
- Quarantined
- Diagnosed
- Repair candidate generated
- Candidate evaluated
- Candidate admitted
- Rollback / rejected
- Recovered but restricted

Every transition should be logged with provenance, evidence, version, authorizing policy, test results and rollback handle.

---

## 9. Decisive experiment backlog

### Experiment A — Can an organ actually be regenerated from surviving organs?

**Minimum setup:** two independently trained specialists with partially overlapping and partially unique tasks; one shared hypernetwork or repair generator; a held-out capability suite.

**Ablations:**
- Remove target checkpoint only.
- Remove checkpoint and all direct adapters.
- Remove target training examples.
- Remove target-specific logs and latent traces.
- Remove one or more surviving organs.
- Corrupt the shared hypernetwork.
- Corrupt the bridge/codec used to transmit target information.
- Compare with a clean external teacher, checkpoint restore, distilled backup, nearest model, direct retraining, and random initialization.

**Controls:** identical total training data, generator parameters, compute, wall-clock, bandwidth and evaluation budget. Record every information channel that remains accessible.

**Outcomes:** exact weight similarity where valid; held-out functional utility; capability breadth; calibration; adversarial robustness; latency; energy; recovery time; privacy leakage; common-mode failure sensitivity.

**Falsification:** if the Holobiont recovery system cannot beat the best feasible backup/retrain baseline after target-specific information has been removed, the stronger regeneration claim is not supported.

### Experiment B — Does localized repair generalize beyond a known teacher?

Replicate SHNN/NSRepair-style repair on a small model, then remove access to the pristine model's activations. Compare:
- repair with clean teacher activations;
- repair with peer-generated predictions;
- repair with stored replay samples;
- repair with a shared hypernetwork;
- repair with no target-specific reference.

Measure both recovery and the rate of false repair: cases where the immune system modifies a healthy component.

### Experiment C — Byzantine immune system under realistic failure mixtures

Use SAC as a baseline. Add:
- correlated model-family errors;
- shared retrieval poisoning;
- bridge/codec corruption;
- false but internally consistent evidence;
- a correct minority specialist;
- adaptive malicious agents that vary messages by recipient;
- evaluator compromise;
- dynamic graph changes.

Compare majority vote, self-reported confidence, receiver-side scoring, trusted external verifier, provenance-aware admission, and hybrid approaches. Measure accuracy, false acceptance, false rejection, cost and recovery time.

### Experiment D — Safe self-modification with recovery contracts

Use a bounded architecture change (e.g. change a route or bridge version) and inject concurrent updates, stale dependencies, partial writes and crashes. Compare:
- full snapshot;
- effect-scoped snapshot;
- write-ahead log / transaction;
- synthesized inverse;
- EvoUndo-style verified recovery;
- combinations selected by a dispatcher.

A mutation is successful only if it improves held-out utility and remains recoverable across counterfactual states.

---

## 10. Pass conclusion and next research direction

The evidence does not justify the treatise's strongest “every organ can regenerate every other organ” claim. It does justify a more precise research programme:

- localized repair is a real, bounded capability;
- generated repair modules and hypernetworks can recover selected behavior under retained reference information;
- decentralized fault filtering can resist some Byzantine influence under explicit graph and evaluator assumptions;
- self-modification must preserve recoverability by design.

**Next priority:** perform the information-accounting experiment for organ regeneration. It is the cleanest way to separate true distributed regeneration from checkpointing, distillation, teacher-assisted repair, or hidden retention of target-specific knowledge.

Implementation remains deferred until the experiment can demonstrate a measurable advantage over those simpler baselines.
