# Pass 15 — Governed Epistemic Utility

Let agent i consider transmitting/requesting message m given receiver state R and coalition state C.

A first-order utility remains conditional information value:

U_info(m) = I(Y; m | R, C)

But information value alone can reward coupling that destroys future independent search. Introduce a diversity-preservation term D_future and governance risk G:

J(m) = I(Y; m | R, C)
       + beta D_future(m)
       - lambda_b B(m)
       - lambda_t T(m)
       - lambda_c Cpl(m)
       - lambda_f Fcorr(m)
       - lambda_g G(m)

where:

- B = bandwidth/token cost;
- T = latency/compute cost;
- Cpl = coupling/convergence cost;
- Fcorr = correlated-failure exposure;
- G = provenance, privacy, authority, safety, and collusion risk.

This should be interpreted as a research objective, not a proven optimal criterion.

## Coalition extension

For a coalition S, define synergy relative to matched isolated computation:

Sigma(S) = V(S) - sum_{i in S} V({i})

and define normalized synergy under resource budget Q as:

Sigma_Q(S) = V_Q(S) - V_Q^*(centralized baseline)

The central Holobiont claim requires Sigma_Q(S) > 0 on tasks where useful information is deliberately partitioned across agents, with confidence intervals and causal sender ablations.

## Independence constraint

Let K_ij denote an empirical failure-correlation or conditional-contribution dependence measure between agents i and j. Rather than maximizing diversity directly, impose:

E[K] <= kappa

for a chosen operating regime, or include a penalty for excessive correlation.

## Important caveat

These quantities are not directly observable from raw embeddings. Functional contribution, causal ablation, failure correlation, and task-specific information must be used. Representation-space cosine similarity is only a proxy and can be misleading.
