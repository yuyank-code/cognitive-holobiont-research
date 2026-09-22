# Falsification Framework — Pass 16 Addendum

## Decisive experiment
Construct tasks where the target function depends on complementary private facts held by different specialists. Randomize ownership of facts across agents while preserving marginal task difficulty.

### Conditions
- centralized single model with equivalent total compute
- centralized model with equivalent total input information
- MoE / routed baseline with equivalent parameter and compute budgets
- independent ensemble + verifier
- conventional text-MAS
- Holobiont candidate with governed epistemic scheduler

### Required controls
- communication-token/bandwidth matching
- memory matching
- verifier budget matching
- sender ablation and sender substitution
- topology edge deletion/addition/rewiring
- agent dropout
- noisy-agent injection
- colluding/adversarial-agent condition
- randomized private-information ownership

### Primary metric
Define coalition synergy as performance above the strongest matched non-communicating or centralized baseline attributable to *unique conditional information*, not merely extra compute or redundancy.

A candidate should not be credited for positive synergy unless:
1. removing the unique-information holder causes a causal degradation on cases requiring that information;
2. substituting a matched irrelevant sender does not reproduce the gain;
3. topology perturbations reveal the communication path that carries the useful dependency;
4. the gain survives bandwidth and verifier matching;
5. the gain remains under held-out information partitions and adversarial/noisy agents.

## Rejection conditions
Reject the strong Holobiont hypothesis if performance is explainable by compute, redundancy, better prompting, or centralized aggregation, or if sender ablation/substitution fails to establish unique conditional contribution.
