# Contradictions and Open Problems — Pass 38
**Date:** 2026-11-23

## Contradictions and tensions

1. **Different families help, but do not guarantee independence.** Five different developers produced lower measured correlation than five samples/personas of one model in one MMLU proof-of-concept, but the cross-family ensemble still had only about two variance-equivalent voters and its plurality lost to its strongest member.
2. **Diversity can predict co-failure, but metrics can mostly measure capability.** NCD-based inferred process diversity predicts lower correlated failure in one 38-model preprint; a separate capability-controlled audit finds several standard diversity measures highly confounded and only a modest co-failure residual.
3. **Distinct errors are not sufficient for collective intelligence.** HiddenBench shows that agents can hold complementary private facts yet fail to elicit them. Response diversity and functional complementarity are separate.
4. **Consensus robustness is conditional.** SAC's graph and local-fault assumptions support information retention/propagation, not truth. Shared evaluator biases can make multiple receivers reject the same correct minority.
5. **Higher individual competence may coexist with greater error correlation.** Better specialists may be more accurate but less independent on some tasks. Selection must optimize capability and dependence jointly, not maximize either alone.
6. **A single diversity scalar is structurally misleading.** Specialists with different roles should be complementary; redundant backups for the same role should exhibit response diversity. One objective cannot represent both.

## Open questions

- Does NCD/IGP add predictive value for agent configurations after including memory, prompts, tools, evaluators, orchestration and interaction history?
- Can response diversity be measured reliably across open-ended tasks, modalities and adversarial perturbations?
- Which model-lineage and data-provenance signals predict common-mode failure after controlling for measured task error correlation?
- Does task-conditioned organ selection outperform choosing a strong individual specialist plus best-of-K?
- How should the system combine an organ's competence, calibration, unique evidence contribution and dependence on already-selected organs?
- Can a network retain useful minority information without becoming vulnerable to collusion or message flooding?
- How do higher-order dependencies and coalitions affect effective redundancy beyond pairwise correlation?
- How does joint training, shared memory or repeated debate change the failure-dependence matrix over time?
- Can the Holobiont maintain independent repair paths when the hypernetwork, codec, memory and evaluator share training lineage?
- What is the right unit of resilience: model, deployed configuration, evidence source, execution path, or dependency lineage?

## Methodological warnings

- Do not call a variance-based effective sample size an information-theoretic count of organs.
- Do not use output similarity as a substitute for error correlation.
- Do not maximize diversity without controlling for competence.
- Do not compare organs on unrelated tasks and then interpret undefined cross-task correlations as independence.
- Do not treat a different provider, tokenizer, architecture or prompt as proof of failure independence.
- Do not infer causal resilience from observational correlation alone; use controlled perturbations and common-mode fault injection.
