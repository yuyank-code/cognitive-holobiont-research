# Source Ledger — Pass 39
**Date:** 2026-11-24

## Peer-reviewed conference papers
1. Zhang et al. (2026), **LatCom: Cross-Agent Latent Compression for Efficient Multi-Agent Collaboration**, EMNLP 2026, pp. 24531–24547. https://aclanthology.org/2026.emnlp-main.1068/  
   Joint multi-sender latent compression; same-family Qwen3 setup; fixed-slot interface; efficiency and accuracy results; explicit limits on heterogeneity and fine-grained code tasks.

2. Mou et al. (2026), **HyLaT: Efficient Multi-Agent Communication via Hybrid Latent–Text Protocol**, EMNLP 2026, pp. 4153–4167. https://aclanthology.org/2026.emnlp-main.181/  
   Multi-round hybrid latent/text communication; small models and limited deployment scale; latent opacity remains.

3. Du et al. (2026), **Enabling Agents to Communicate Entirely in Latent Space**, ACL 2026 Long Papers. https://aclanthology.org/2026.acl-long.1248/  
   Interlat latent communication. Included as a peer-reviewed neighboring method; not treated as proof of universal heterogeneous semantic transfer.

## Preprints
4. Zhang & Emu (2026), **Do Latent Channels Actually Communicate? A Causal Audit of Latent Multi-Agent LLM**, arXiv:2607.26773. https://arxiv.org/abs/2607.26773  
   Four message conditions and five measures; separates message presence, message identity, example-specific content and separate-agent value.

5. Cheng, Das & Ramnath (2026), **When Does Latent Communication Pay? A Causal Audit of Relayed KV Caches in Multi-Agent LLMs**, arXiv:2608.04893. https://arxiv.org/abs/2608.04893  
   True/deranged/zero/random cache interventions; calibrated receiver-necessity and natural benchmark regimes; native relay, KVComm and C2C comparisons.

6. Chen et al. (2026), **See What I See, Know What I Think: Dense Latent Communication Across Heterogeneous Agents**, arXiv:2606.13594v2. https://arxiv.org/abs/2606.13594  
   Learned KV alignment across Qwen size pairs and Mistral-to-Qwen; three-agent document sharing; pair-specific adapter, payload and generalization limits.

7. Piepereit (2026), **Architecture-Dependent Causal Transfer of Activation States Across Large Language Models**, arXiv:2608.16347. https://arxiv.org/abs/2608.16347  
   Small/medium open-weight models; representational similarity, retrieval and causal activation-injection levels; one modest positive pair among three tested decoder-only pairs.

8. Liu (2026), **BOUNDARY_SYNC: Measuring Communication-Induced Representational Coupling in Multi-Agent LLM Systems**, arXiv:2607.01600. https://arxiv.org/abs/2607.01600  
   Communication-induced output homogenization preprint; limitations include self-anchoring and prompt-length/group-size confounds and one task domain.

9. Brito & Baquero (2026), **When Latent Agents Lie: KV-Cache Integrity in Multi-Agent LLM Collaboration**, arXiv:2606.28958. https://arxiv.org/abs/2606.28958  
   Hidden-state tampering, visible-verifier limitations, HMAC transport integrity; endpoint semantic truth remains outside the MAC guarantee.

10. Liu (2026), **Beyond tokens: a unified framework for latent communication in LLM-based multi-agent systems**, arXiv:2606.05711. https://arxiv.org/abs/2606.05711  
    Survey taxonomy of latent object, alignment and receiver fusion approaches.

## Evidence discipline
The two causal audits and KV-integrity work are preprints. Their results should be treated as important methodological evidence requiring independent replication, not settled consensus. The EMNLP/ACL papers are peer-reviewed but still have bounded model sizes, task families and deployment settings. No source demonstrates the complete Cognitive Holobiont.
