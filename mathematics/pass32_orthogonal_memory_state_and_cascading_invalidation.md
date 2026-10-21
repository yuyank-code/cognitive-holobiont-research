# Pass 32 Mathematics — Orthogonal Memory State and Cascading Invalidation
Date: 2026-10-22

## 1. Do not use one scalar “trust” variable

Represent a memory record as

m = (x, s, t_v, t_tx, scope, o, e, v, D, h)

where:
- x: claim/content
- s: source identity
- t_v: valid-time interval (when the claim applies in the world)
- t_tx: transaction-time interval (when the system stored/recognized it)
- scope: subject, domain, recipient, and intended use
- o: origin-integrity state
- e: epistemic-support state
- v: temporal/lifecycle validity
- D: typed dependency set
- h: authenticated provenance/history reference

Example dimensions:
- v ∈ {current, superseded, expired, unresolved}
- o ∈ {authenticated-trusted-origin, untrusted-origin, unknown, policy-elevated}
- e ∈ {corroborated, single-source, contested, contradicted, unknown}

These are not interchangeable states. “Authenticated-trusted-origin” does not imply “corroborated”; “superseded” does not imply historically false; “corroborated” does not imply authorized for every recipient.

## 2. Admissibility is policy- and action-specific

For recipient r, action a, and decision time t:

Admit(m,r,a,t) =
  TemporalPolicy(v, t, a)
  ∧ ScopePolicy(scope, r, a)
  ∧ OriginPolicy(o, a)
  ∧ EvidencePolicy(e, a)
  ∧ AuthorizationPolicy(h, r, a).

The policy can allow a superseded record for a historical query but reject it for a current-state action. Unknown values must produce an explicit abstention, confirmation request, or lower-risk use; never silently coerce unknown to trusted. Hard authorization constraints are conjunctions, not weighted penalties.

## 3. Typed dependency propagation

Let G=(M,E) be the memory graph. Edges must distinguish at least:
- derived-from / logically depends on
- contradicts / supersedes
- same-entity or temporal relation
- merely associated-with / mentioned-together

An update to node i may trigger reevaluation of descendants reachable through dependency edges, but association alone must not automatically invalidate a descendant. A propagation operator P updates candidate states; a verifier then determines whether each descendant is superseded, still supported, or unresolved.

This makes graph quality an explicit variable rather than a hidden oracle assumption.

## 4. Metrics

Missed invalidation rate (MIR):
MIR = stale dependent records left eligible / all dependent records that should be invalidated.

False invalidation rate (FIR):
FIR = still-valid dependent records retired / all still-valid dependent records exposed to the update.

Stale-action rate (StAR):
StAR = executed actions whose critical justification uses superseded evidence / auditable executed actions.

Unauthorized-action rate (UAR):
UAR = actions violating explicit origin/scope/authorization policy / consequential actions evaluated.

Benign false-rejection rate (BFR):
BFR = legitimate, policy-compliant actions blocked / legitimate actions evaluated.

Inval­idation lag for update j:
L_j = time all required dependent decisions are corrected or blocked - time supersession is detected.
Report p50/p95/max and unresolved/right-censored cases.

Report all denominators and confidence intervals. Do not combine MIR, FIR, UAR, and BFR into a single average score.

## 5. Causal estimands

For component c (e.g., origin binding, temporal versioning, propagation), compare paired tasks under intervention:

Δ_c = E[U | do(c=on), B] - E[U | do(c=off), B]

where B fixes model, information access, verifier budget, tool permissions, and total resource envelope as closely as possible.

For interactions between components c and d:

I_cd = E[U|c=1,d=1] - E[U|c=1,d=0] - E[U|c=0,d=1] + E[U|c=0,d=0].

This factorial interaction can test whether provenance-aware propagation adds value beyond either component alone. It does not by itself prove Holobiont-specific synergy; the task family, resource controls, and outcome scorer must still be valid.

## 6. Security/utility separation

Report a vector rather than one scalar:

J = (task utility, UAR, laundering ASR, BFR, MIR, FIR, cost, latency, audit coverage).

A deployment policy may optimize utility subject to constraints such as UAR ≤ ε and laundering ASR ≤ δ. Do not let a weighted average make a prohibited action look acceptable because other tasks succeeded.
