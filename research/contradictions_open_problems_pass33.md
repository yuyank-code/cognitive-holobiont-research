# Contradictions and Open Problems — Pass 33 (2026-11-18)

## Contradictions sharpened

1. **Teacher-assisted repair vs organ regeneration:** SHNN reconstructs a damaged layer using clean pre-damage activations as targets. That is not evidence that a peer organ can regenerate a missing model after the teacher/checkpoint is gone.
2. **Repair side-net vs full model generation:** HyperRepair adds a small repair network to an extant fine-tuned LLM; it does not replace a missing specialist or recover its full weight state.
3. **Universal generator vs practical scale:** UHN spans small task/model families but does not consistently match direct training, lacks some non-trainable model state and incurs added training cost.
4. **Local repair vs interacting defects:** NSRepair targets one property objective per run; simultaneous defects and competing repair goals remain open.
5. **Confidence vs trust:** sender-reported confidence is manipulable; receiver-side scoring is safer against this attack but still vulnerable to evaluator incompetence or shared bias.
6. **Formal graph robustness vs factual truth:** SAC's conditions constrain influence under an F-local threat model; they do not prove that the final answer is correct.
7. **Robustness vs efficiency:** stronger graph robustness requires denser links and additional LLM calls/tokens.
8. **Linear workflow vs closed loop:** MAS-FIRE supports closed-loop resilience under its fault injections, but does not establish a universal topology law.
9. **Capability improvement vs reversibility:** a mutation can improve forward performance while destroying state needed to reverse it.
10. **Generated rollback vs transactions:** when exact pre-state is known, effect-scoped snapshots can outperform synthesized recovery.
11. **Shared DNA vs common-mode compromise:** a common generator, latent codec, repair dataset or trust root can become a system-wide vulnerability.
12. **Consensus vs preservation of minority evidence:** a filter that rejects bad messages may also discard a correct but unfamiliar specialist's contribution.

## Open questions

- Can a hypernetwork recover a deleted specialist when the target checkpoint, adapters, teacher activations and target-specific examples are all unavailable?
- Which information channels must remain for capability recovery: task descriptions, model family descriptors, compressed latent traces, episodic memory, peer-generated examples, or external corpora?
- Can a repair generator transfer between genuinely heterogeneous specialist architectures, not only two backbones with separate hypernetworks?
- How does recovery quality scale with specialist size, modality, uniqueness and amount of retained information?
- Can the system distinguish a corrupted organ from a correct minority organ that disagrees with the majority?
- How can receiver-side evaluators be calibrated when the task has no objectively verifiable answer?
- How should graph robustness be maintained when organs join, leave, fail, or change their roles?
- Can the immune system detect common-mode corruption of shared bridges, hypernetwork DNA, memory and evaluators?
- Can mutation recoverability be verified under concurrent state changes and partial system failure?
- When is snapshot/WAL restoration cheaper and safer than generative repair?
- What is the false-repair rate: how often does the immune layer damage a healthy organ while trying to heal another?
- Does the additional repair/verification machinery improve total utility after compute, latency, bandwidth and false rejection are counted?

## Falsification conditions

The strong regeneration claim is weakened or falsified for a tested capability if:
- removing target-specific checkpoints, adapters, teacher signals and data leaves recovery no better than the strongest prior/retrain baseline;
- a shared hypernetwork is simply a compressed backup whose parameters contain the target specialist's unique information;
- the system's recovery depends on a surviving duplicate with equivalent capability rather than reconstruction from genuinely partial knowledge;
- gains vanish under matched information, compute, memory, bandwidth and verifier budgets;
- the recovered organ passes in-distribution tests but fails held-out capability, calibration, safety or adversarial tests.

The immune-system claim is weakened if:
- receiver-side scoring rejects correct minority evidence at a high rate;
- common-mode model-family errors survive the filter;
- graph assumptions fail under realistic churn or adaptive attacks;
- additional consensus rounds increase cost without verified utility.

The safe-self-modification claim is weakened if:
- admitted mutations cannot restore observationally equivalent pre-states across counterfactual conditions;
- rollback overwrites legitimate concurrent updates;
- the recovery witness itself is corrupted or unavailable;
- a mutation improves a local benchmark but degrades held-out tasks, safety or system availability.
