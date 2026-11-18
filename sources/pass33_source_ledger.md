# Source Ledger — Pass 33 (2026-11-18)

## HyperRepair: Recovering Forgotten General Capabilities of Fine-Tuned Language Models
- Authors: Junrong Tang, Jianghui Wang, Hao Kong, Yang Lin, Yibo Yang.
- Date/status: arXiv preprint posted 30 October 2026; not peer reviewed in this pass.
- Link: https://arxiv.org/abs/2610.41147
- Use: hypernetwork-generated repair side-nets for forgotten general capabilities in LoRA-adapted LLMs.
- Scope: Qwen2.5-7B and Llama-3.1-8B; 12 LoRA adaptation domains; 15 general benchmarks; held-out adaptation domains.
- Key reported result: 93.4% of base average general score and 99.5% of fine-tuned average domain score on default split.
- Limits: existing base/adapted model remains; small generated RSN, not full specialist; separate HyperNet per backbone; no organ-deletion test.

## Universal Hypernetworks for Arbitrary Models
- Author: Xuanfeng Zhou.
- Date/status: arXiv preprint posted 2 April 2026; not peer reviewed in this pass.
- Link: https://arxiv.org/abs/2604.02215
- Code: https://github.com/Xuanfeng-Zhou/UHN
- Use: descriptor-conditioned weight generation across model architecture/task families and recursive hypernetwork generation.
- Scope: vision, graph, text classification and formula regression; single RTX 4090; recursive generation to three intermediate UHN levels on MNIST MLP.
- Limits: direct-training performance gaps; missing non-trainable state such as BatchNorm running statistics; added compute/memory; cross-task interference; no LLM-scale deleted-specialist recovery.

## Self-healing neural networks via modular patch layers for diverse structural and adversarial damages
- Authors: B. Santhosh Reddy et al.
- Date/status: Scientific Reports, published 22 June 2026; open access.
- Link: https://www.nature.com/articles/s41598-026-57677-x
- Use: activation-discrepancy localization and local patch repair.
- Scope: MNIST, Fashion-MNIST, Sign Language MNIST, CIFAR-10; mainly MLPs, with a CIFAR-10 CNN test.
- Limits: clean pre-damage activations are used as repair targets; deeper CNN recovery is partial; transformer and multi-layer validation remain future work.

## Neural Network Repair With Shapley-Guided Search
- Authors: Xiaofu Du, Zixiong Zhang, Xuesong Wang, Linqiang Liu, Junyan Qian.
- Date/status: CAAI Transactions on Intelligence Technology, first published 11 May 2026; open access.
- DOI: https://doi.org/10.1049/cit2.70147
- Code/data pointer: https://doi.org/10.5281/zenodo.17494304
- Use: Shapley-based neuron fault localization and multi-objective repair balancing defect reduction and preservation.
- Scope: local robustness, fairness, backdoor removal and safety; LeNet-style, ResNet, VGG and small MLP models.
- Limits: Shapley estimation expensive beyond roughly 100M parameters; one defect objective per run; sequential decision repair is not addressed.

## Robust Multi-Agent LLMs under Byzantine Faults
- Authors: Haejoon Lee, Vincent-Daniel Yun, Dimitra Panagou, Sai Praneeth Karimireddy.
- Date/status: EMNLP 2026, peer-reviewed conference proceedings, pages 44639–44657.
- DOI: https://doi.org/10.18653/2026.emnlp-main.1960
- Official page: https://aclanthology.org/2026.emnlp-main.1960/
- Preprint: https://arxiv.org/abs/2605.09076
- Use: Self-Anchored Consensus; receiver-side scoring/filtering and (F+1)-robust graph conditions.
- Scope: small networks (7 and 9 agents), static graph, F-local threat model, single-turn math/commonsense tasks.
- Limits: evaluator competence is required; a faulty evaluator may reject correct evidence; dynamic graphs, multi-turn reasoning and tool use outside scope; denser graphs cost more.

## Rethinking the Reliability of Multi-agent System: A Perspective from Byzantine Fault Tolerance
- Authors: Lifan Zheng et al.
- Date/status: AAAI-26, published 14 March 2026, Proceedings of AAAI 40(41), 35012–35020.
- DOI: https://doi.org/10.1609/aaai.v40i41.40806
- Preprint: https://arxiv.org/abs/2511.10400
- Use: CP-WBFT confidence-probe-based weighted Byzantine consensus.
- Limits: task/topology-specific results; small curated samples in reviewed analysis; sender confidence is manipulable, as explicitly discussed by the later SAC work.

## MAS-FIRE: Fault Injection and Reliability Evaluation for LLM-Based Multi-Agent Systems
- Authors: Jin Jia, Zhiling Deng, Zhuangbin Chen, Yingqi Wang, Zibin Zheng.
- Date/status: arXiv preprint posted 23 February 2026; publication status not confirmed in this pass.
- Link: https://arxiv.org/abs/2602.19843
- Use: 15-fault taxonomy and process-level fault-injection evaluation; reports benefits for iterative closed-loop topologies over linear workflows.
- Scope: three representative MAS architectures; prompt, response and routing fault injection.
- Limits: architecture and injected-fault coverage bounded; independent replication and matched-cost comparison needed.

## EvoUndo: Recoverability-Constrained Self-Evolution for LLM Agent Harnesses
- Authors: Tanmay Sah, Dolly Sah, Harshul Jain, Tanya Sah.
- Date/status: arXiv preprint posted 28 August 2026; not peer reviewed in this pass.
- Link: https://arxiv.org/abs/2608.28363
- Use: counterfactual verification of recoverability for persistent self-modifications.
- Scope: 600 unseen one-shot self-evolution tasks; controlled and natural recovery failures; comparisons with effect-scoped snapshots.
- Limits: harness mutation tasks, not multi-organ neural architecture self-modification; recovery-language and state-grounding dependence; no complete production WAL runtime.
