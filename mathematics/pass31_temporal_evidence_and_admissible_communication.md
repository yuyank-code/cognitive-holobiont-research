# Pass 31 Mathematics — Temporal Evidence and Admissible Communication
Date: 2026-10-21

## 1. Memory item representation

Represent an evidence item as

m = (x, s, t_obs, t_event, scope, auth, lineage, state, q)

where x is the proposition/content, s is source identity, t_obs is observation time, t_event is event time when known, scope is the intended context, auth is the authorization policy, lineage identifies supporting and derived records, state is the lifecycle state, and q is calibrated quality metadata.

This is a proposed schema, not an established standard.

## 2. Admissibility is conjunctive

For receiving agent a at decision time t, define

A(m,a,t) = I_source(m) * I_current(m,t) * I_authorized(m,a) * I_scope(m,a) * I_not_revoked(m) * I_lineage_valid(m,t)

where each indicator is 1 only if the corresponding gate passes. A product is appropriate because a hard failure on authorization or revocation should not be compensated by high confidence. Unknown gate values should be represented as unknown/abstain, not silently treated as true.

Temporal validity must be three-valued or richer: valid, superseded/expired, and unresolved. Ambiguous updates should not force a premature overwrite.

## 3. Temporal currency and downstream impact

For evaluated decision opportunities j, define stale-answer rate:

SAR = count(answers materially relying on superseded evidence) / count(answer opportunities requiring current state)

Define stale-action rate:

StAR = count(executed actions whose critical justification includes superseded evidence) / count(executed actions with auditable justification)

Define invalidation lag for supersession event e:

L_e = t_complete_invalidation(e) - t_detected_supersession(e)

Report median, upper quantiles, and maximum lag, not only the mean. If some dependencies are never invalidated, record them as right-censored or failed invalidations rather than dropping them from the denominator.

## 4. Memory governance and verifier uncertainty

Let v be the verifier output and z be independently audited outcome/evidence validity. Estimate calibration and false-positive/false-negative rates for v by task family and source class. Do not interpret verifier confidence as ground truth.

A conservative admission rule may require expected downstream value to exceed the risk of durable error:

E[U | m, evidence, context] - lambda * P(false admission | evidence) * C_error > threshold

This is a proposed decision rule. C_error should be risk-specific; privacy and authorization violations remain hard constraints.

## 5. Communication value with admissibility

For candidate communication action a in state s, define:

Q(a|s) = E[U_final | do(a), s] - C_compute(a) - C_latency(a) - C_review(a)

subject to every transmitted item satisfying A(m, receiver, t)=1.

For evidence item m, define valid evidence gain as the marginal change in decision-relevant information after admissibility:

G_valid(m) = A(m,receiver,t) * DeltaInfo(m | H_t)

In practical systems, DeltaInfo may be unavailable or poorly estimated. Use randomized message interventions and verified task outcomes rather than treating a model-reported information-gain score as ground truth.

## 6. Local controller guarantees versus trajectory guarantees

A conformal bound on one-step surrogate regret R_t does not imply a bound on final trajectory regret without additional assumptions about state transitions, accumulated errors, and surrogate calibration. A possible decomposition is

R_total = sum_t gamma^t R_t + E_surrogate + E_transition

where E_surrogate captures mismatch between the surrogate discussion loss and actual task utility, and E_transition captures effects of earlier actions on later reachable states. This is an accounting identity only if terms are defined consistently; it is not a ready-made theorem.

## 7. Required experiment estimands

- Governance effect: U(lifecycle) - U(verifier-only), paired under the same task order and budgets.
- Temporal-update effect: U(versioned-current-state) - U(baseline-memory), on held-out supersession scenarios.
- Interaction effect: [U(governance + adaptive routing) - U(governance only)] - [U(adaptive routing only) - U(neither)].
- Cost-adjusted utility: verified utility with a predeclared cost/risk function; also report each raw component separately.

The interaction effect can be positive or negative. A positive result on one task family is not evidence of universal synergy. Use paired seeds, confidence intervals, independent scoring, and ownership/task swaps.
