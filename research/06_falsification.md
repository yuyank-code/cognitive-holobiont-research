# Falsification Framework

The architecture must be exposed to experiments capable of disproving its central claims.

## Latent communication

A latent bridge should not be considered successful merely because the receiver improves. Controls must determine whether information was genuinely transmitted, already present in the receiver, leaked through shared training data, or reproduced by ordinary ensemble effects.

### Required causal controls

- valid sender/example message;
- mismatched sender/example message;
- zero/no message;
- bandwidth- and norm-matched random message;
- other-example message;
- cross-agent/cross-model controls where feasible.

Primary endpoint for sender-specific transfer: paired-message effect after controlling for message presence and bandwidth. Report confidence intervals and equivalence tests where the claim is null.

## Specialization

Compare independently trained specialists, shared-backbone specialists, MoE experts, adapters, and Holobiont organs. Measure task specialization, intervention-defined capability, error correlation, OOD correlation, and epistemic diversity. Do not equate parameter distance with independence.

## Consensus

Measure accuracy, calibration, diversity, minority preservation, correlated errors, communication cost, and adversarial susceptibility. Include diversity-aware initialization, calibrated confidence, and abstention baselines. Agreement alone is not a success criterion.

## Regeneration

Destroy or remove an organ under controlled conditions. Compare no-repair, ordinary retraining, checkpoint restoration, distillation, hypernetwork reconstruction, and distributed-code reconstruction. Evaluate capability equivalence, robustness, calibration, OOD behavior, conflict with surviving priors, collateral regression, and resource cost. Parameter similarity is not sufficient evidence of regeneration.

## Common-mode failure

Corrupt shared components independently: backbone, bridge, memory, hypernetwork, routing, evaluator, constitution, and topology controller. Measure both individual failure probability and pairwise/joint failure correlation. Vary redundancy and estimate the point at which additional redundancy ceases to reduce system risk.

## Immune system

Introduce benign unusual specialists, naturally uncertain specialists, corrupted specialists, poisoned specialists, strategically malicious specialists, and truthful-but-misleading coalitions. Measure false quarantine, missed detection, evidence-lineage contamination, and useful-minority loss.

## Communication topology

Vary topology family, edge count, message frequency, and bandwidth independently. Test whether adaptive topology improves the utility/cost Pareto frontier while preserving diversity and security. Attack the topology controller itself and test recovery from routing paralysis.

## Abstention

Construct beyond-capability and ambiguous tasks with calibrated ground truth. Compare forced-answer consensus with confidence-aware abstention. Measure whether abstention reduces common-mode hallucination without excessively suppressing solvable tasks.

## Recursive modification

Require self-modification to improve a predefined held-out objective while preserving prior capabilities. Test for capability regression, reward hacking, training-distribution overfitting, irreversible architectural damage, and deceptive evaluation behavior. Dynamic-weight methods must be evaluated on held-out distributions rather than training loss alone.

## Novelty test

Before claiming that Holobiont is a new architecture, reproduce strong baselines from MoE, multi-agent, ensemble, model-stitching, modular-network, parameter-efficient adaptation, and self-healing literature. Match total compute, active parameters, communication bandwidth, memory, and redundancy. Include a single-model multi-output/self-conditioning baseline.
