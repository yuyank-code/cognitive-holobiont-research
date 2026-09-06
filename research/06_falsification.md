# Falsification Framework

The architecture must be exposed to experiments capable of disproving its central claims.

## Run 18 additions

### Effective-channel hypothesis

Measure raw N and K_eff before/after communication. Test whether task performance, robustness, and marginal utility correlate more strongly with K_eff than N. Include homogeneous and heterogeneous agents and single-model multi-output baselines.

### Coupling phase diagram

Sweep group size, topology density, communication frequency, and bandwidth. Estimate coupling ratio C together with behavioral diversity and joint failure correlation. The hypothesis is not that communication always helps or always hurts, but that useful regimes exist and are identifiable.

### Diversity-metric triangulation

Require at least four classes of measurement: representation similarity, behavioral disagreement, failure correlation, and intervention-based causal dependence. A system cannot claim independence from a single embedding metric.

### Dependency-aware confidence

Correlate confidence with correctness after conditioning on shared evidence and communication ancestry. Compare naive confidence weighting with dependency-aware weighting and abstention.

### Truthful-collusion attack

Construct coalitions that provide individually true fragments designed to produce a false global inference. Test whether provenance-only, confidence-only, majority, dependency-aware fusion, and contradiction-aware fusion can resist the attack.

## Existing framework

### Latent communication

A latent bridge should not be considered successful merely because the receiver improves. Controls must determine whether information was genuinely transmitted, already present in the receiver, leaked through shared training data, or reproduced by ordinary ensemble effects.

Required controls: valid sender/example message; mismatched sender/example; zero/no message; bandwidth/norm-matched random message; other-example message; cross-agent/cross-model controls where feasible.

### Specialization

Compare independently trained specialists, shared-backbone specialists, MoE experts, adapters, and Holobiont organs. Measure task specialization, intervention-defined capability, error correlation, OOD correlation, and epistemic diversity. Do not equate parameter distance with independence.

### Consensus

Measure accuracy, calibration, diversity, minority preservation, correlated errors, communication cost, and adversarial susceptibility. Include diversity-aware initialization, calibrated confidence, evidence-weighted fusion, and abstention baselines. Agreement alone is not a success criterion.

### Regeneration

Destroy or remove an organ under controlled conditions. Compare no-repair, ordinary retraining, checkpoint restoration, distillation, hypernetwork reconstruction, and distributed-code reconstruction. Evaluate capability equivalence, robustness, calibration, OOD behavior, conflict with surviving priors, collateral regression, and resource cost. Parameter similarity is not sufficient evidence of regeneration.

### Common-mode failure

Corrupt shared components independently: backbone, bridge, memory, hypernetwork, routing, evaluator, constitution, and topology controller. Measure both individual failure probability and pairwise/joint failure correlation. Vary redundancy and estimate the point at which additional redundancy ceases to reduce system risk.

### Immune system

Introduce benign unusual specialists, naturally uncertain specialists, corrupted specialists, poisoned specialists, strategically malicious specialists, and truthful-but-misleading coalitions. Measure false quarantine, missed detection, evidence-lineage contamination, and useful-minority loss.

### Communication topology

Vary topology family, edge count, message frequency, and bandwidth independently. Test whether adaptive topology improves the utility/cost Pareto frontier while preserving diversity and security. Attack the topology controller itself and test recovery from routing paralysis.

### Abstention

Construct beyond-capability and ambiguous tasks with calibrated ground truth. Compare forced-answer consensus with confidence-aware abstention. Measure whether abstention reduces common-mode hallucination without excessively suppressing solvable tasks.

### Recursive modification

Require self-modification to improve a predefined held-out objective while preserving prior capabilities. Test for capability regression, reward hacking, training-distribution overfitting, irreversible architectural damage, and deceptive evaluation behavior. Dynamic-weight methods must be evaluated on held-out distributions rather than training loss alone.

### Novelty test

Before claiming that Holobiont is a new architecture, reproduce strong baselines from MoE, multi-agent, ensemble, model-stitching, modular-network, parameter-efficient adaptation, and self-healing literature. Match total compute, active parameters, communication bandwidth, memory, and redundancy. Include a single-model multi-output/self-conditioning baseline.
