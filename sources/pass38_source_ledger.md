# Source Ledger — Pass 38
**Date:** 2026-11-23

## New sources

1. **Morante, Santiago & Romero García-Rubio, Marta (2026).** “Correlation limits the reliability of ensemble decision making with large language models.” *Discover Informatics*, 1, article 35. Published 4 November 2026. Open-access peer-reviewed journal article. DOI: https://doi.org/10.1007/s44564-026-00040-z  
   Use: variance-based effective sample size under correlated votes; proof-of-concept comparison of same-model samples/personas with different model families.  
   Limits: exchangeable/equal-competence theory; small 562-item MMLU proof-of-concept; task-dependent correlation; majority/plurality model does not capture all collaboration.

2. **Tieman, Ross & Markou, Evan (2026).** “Inferred Generative-Process Diversity Predicts Correlated Failure Across Language Models.” arXiv:2609.03422, submitted 3 September 2026. Preprint. https://arxiv.org/abs/2609.03422  
   Use: output-derived NCD residual predicts cross-task correlated wrong-answer agreement beyond semantic distance and capability.  
   Limits: preprint; 38 models, 100 open-ended prompts, ten benchmark families; no agent harness/tools in primary experiment; NCD residual is not a recovered mechanism or true metric; association is not causal.

3. **Kim, Donghwan (2026).** “Are Diversity Metrics Measuring Diversity? A Capability-Controlled Audit of Majority-Vote Gain in LLM Ensembles.” arXiv:2607.20768, submitted 22 July 2026. Preprint. https://arxiv.org/abs/2607.20768  
   Use: 31,900 subsets, capability confounding, limited majority-vote gains over strongest member.  
   Limits: single-author preprint; majority-vote focus; MMLU-Pro and TruthfulQA; does not test learned routing, private-evidence collaboration or fault recovery.

4. **Baek, David D. et al. (2026).** “D-FUSEr: Diverse Failure, Unified Success via Error-Distribution Shaping in LLM Reasoning.” ICML 2026, PMLR 306:5031–5063. https://proceedings.mlr.press/v306/baek26a.html  
   Use: diverse-failure reward and anti-votes; theory and experiments across three model families/four benchmarks.  
   Limits: bounded benchmarks and aggregation/refinement settings; not a Holobiont fault-tolerance demonstration.

5. **Li, Yuxuan, Naito, Aoi & Shirado, Hirokazu (2026).** “Systematic Failures in Collective Reasoning under Distributed Information in Multi-Agent LLMs.” ICML 2026, PMLR 306:69250–69268. https://proceedings.mlr.press/v306/li26ej.html  
   Use: HiddenBench; 65 tasks; collective failure to elicit latent private information; structured communication improvement.  
   Limits: benchmarked task families and interaction protocols; not a general proof about all specialist federations.

6. **Lee, Haejoon et al. (2026).** “Robust Multi-Agent LLMs under Byzantine Faults.” arXiv:2605.09076. Preprint. https://arxiv.org/abs/2605.09076  
   Use: receiver-side evaluation, bounded filtering, F-local Byzantine model and (F+1)-robust graph assumptions.  
   Limits: small 7–9 agent networks, fixed graphs, focused tasks; receiver evaluation can be wrong; guarantees concern information propagation under assumptions, not truth.

## Foundational prior source used for context

7. **Kim, Elliot Myunghoon et al. (2025).** “Correlated Errors in Large Language Models.” ICML 2025, PMLR 267:30038–30066. https://proceedings.mlr.press/v267/kim25e.html  
   Use: >350-model study; correlated errors and provider/architecture effects.  
   Status: peer-reviewed conference paper; older than this pass and used as supporting context, not counted as the main new result.
