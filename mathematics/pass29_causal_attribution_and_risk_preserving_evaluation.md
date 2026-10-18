# Mathematics Addendum — Pass 29: Counterfactual Influence, Coalition Value, Risk Vectors

## Counterfactual debate contrasts
Let U be independently verified task utility and P denote peer exposure.

\[
\Delta_{self}=E[U\mid do(P=self\text{-}reflection)]-E[U\mid do(P=initial\ only)]
\]
\[
\Delta_{stance}=E[U\mid do(P=stance\text{-}only)]-E[U\mid do(P=self\text{-}reflection)]
\]
\[
\Delta_{rationale}=E[U\mid do(P=full\ rationale)]-E[U\mid do(P=stance\text{-}only)].
\]

These are proposed experimental contrasts; they need not add to a total causal effect under arbitrary interactions. Randomize conditions and report beneficial and harmful transitions separately.

## Background-conditioned marginal contribution
For coalition S and agent i not in S:

\[
\Delta_i(S)=E[U\mid do(S\cup\{i\})]-E[U\mid do(S)].
\]

For agents i and j, interaction in background S is:

\[
\Delta_{ij}(S)=Q(S\cup\{i,j\})-Q(S\cup\{i\})-Q(S\cup\{j\})+Q(S).
\]

Contribution may depend on S. Positive interaction is context-specific and does not establish novelty or consciousness. If exhaustive coalition evaluation is infeasible, sample coalitions prospectively and report uncertainty and unobserved-coalition limits.

## Risk-constrained objective
Let r = (stale, conflict, leakage, revoked-memory reuse, constraint decay, summary contamination). Maximize expected verified utility subject to preregistered per-risk limits r_k(pi) <= epsilon_k for every risk k, plus hard authorization and privacy constraints. A high average score must not compensate for prohibited disclosure. Justify risk limits before observing results.

## Risk-aware benchmark subset
\[
\Psi(S)=\alpha\rho_{rank}(S)+\beta\,coverage_{risk}(S)+\gamma\,detection_{high\ risk}(S).
\]
This is a design objective, not a universal formula. Publish weights, reference models, held-out tests, and risk coverage. Deterministic selection does not eliminate uncertainty under distribution shift.

## Measurement caveat
Trace instrumentation records events; observational graphs do not identify causal effects. Deterministic checks can encode faulty specifications and judges can misattribute failures. Combine telemetry with randomized interventions, independent outcome oracles, scorer mutation tests, and adjudication.
