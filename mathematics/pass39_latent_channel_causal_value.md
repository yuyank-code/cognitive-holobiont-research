# Mathematical Formalization — Pass 39
**Date:** 2026-11-24  
**Topic:** Causal value and governance of latent communication.

## 1. Message-boundary model

Let:
- q be the current task;
- X_R be receiver-visible local context;
- S_i be sender-private evidence for example i;
- M_i = φ(q,S_i; θ_S) be the sender's latent payload;
- Y = f(q,X_R,M; θ_R, ε) be the receiver output under fixed receiver parameters and decoding randomness.

The intervention boundary is immediately after sender payload construction and immediately before receiver injection. In each contrast, hold receiver weights, local context, prompt surface, decoding and downstream computation fixed; change only the payload.

## 2. Four core message conditions

- M_0: no payload.
- M_cur: current-example sender payload.
- M_oth: length/geometry-matched payload from a different example.
- M_self: receiver-generated payload under a matched computation budget.

For private-evidence calibration, add M_intact: sender processes an answer-irrelevant but format-matched private-evidence record.

## 3. Separate estimands

Let U(M) be independently scored receiver utility.

**Presence effect**
PL = D(P_cur, P_0), where D is a declared prediction-distribution divergence. This measures receiver sensitivity to message presence, not task utility.

**Content-identity effect**
CIC = D(P_cur, P_oth). This measures whether payload identity changes receiver predictions.

**Content-attributable gain**
CAG = E[U(M_cur)] − E[U(M_oth)].

**Separate-agent value**
SSG = E[U(M_cur)] − E[U(M_self)].

**Pairing effect**
τ_pair = E[U | do(M=M_cur)] − E[U | do(M=M_oth)].

**Generic interface/computation effect**
τ_generic = E[U | do(M=M_oth)] − E[U | do(M=M_0)].

**Private-content effect**
τ_private = E[U | do(M=M_cur)] − E[U | do(M=M_intact)].

The algebraic identity:
U(M_cur) − U(M_0) = [U(M_oth) − U(M_0)] + [U(M_cur) − U(M_oth)]
separates generic payload-presence value from example-pairing value. This is an accounting decomposition; it does not imply independent underlying mechanisms.

A positive CAG does not imply positive SSG. A positive PL or CIC does not imply positive task utility. A positive true-versus-zero effect does not prove example-specific information transfer.

## 4. Conditional information contribution

For a coalition S of organs and receiver state R, define the marginal utility of organ i:
Δ_i(S | R) = U(R ∪ S ∪ {i}) − U(R ∪ S).

For a pair i,j, define interaction:
I_ij(S | R) = U(R ∪ S ∪ {i,j}) − U(R ∪ S ∪ {i}) − U(R ∪ S ∪ {j}) + U(R ∪ S).

These should be computed under randomized evidence ownership, sender ablation, and receiver context controls. A positive interaction is not enough by itself: it must predict independently verified held-out utility.

## 5. Total-cost objective

For channel c, define:
J(c) = U_verified(c) − λ_F F(c) − λ_B B(c) − λ_L L(c) − λ_M M(c) − λ_T T_adapter(c) − λ_R R_security(c).

Where:
- F: total model FLOPs/compute;
- B: bytes transmitted and stored;
- L: end-to-end latency;
- M: peak and persistent memory;
- T_adapter: adapter training, calibration and maintenance cost;
- R_security: measured integrity/privacy/failure risk under a declared threat model.

Report Pareto frontiers and component costs. Do not collapse incomparable costs into a single scalar without sensitivity analysis.

## 6. Integrity and semantic validity are distinct

Let Auth(payload, metadata) indicate that a payload is authentic and unchanged in transit. Let Valid(payload, evidence, task) indicate that it is semantically supported and authorized.

Auth = 1 does not imply Valid = 1.

An HMAC/signature can protect the transport boundary under uncompromised keys. Endpoint compromise, false evidence, poisoned model state and misleading visible commitments require separate controls.

## 7. Conditional routing policy

Let N_R be the receiver's missing information/uncertainty, V_i the expected marginal utility of sender i, and C_i the full channel cost. A latent transfer should be selected only when:
E[Δ_i | receiver necessity, task, evidence] > C_i + risk_margin,
and the channel has passed pair-specific interoperability and integrity checks.

This is a proposed decision rule, not an empirically validated universal threshold.
