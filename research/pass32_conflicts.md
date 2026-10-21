# Pass 32 — Contradictions and Failure Boundaries
Date: 2026-10-22

## C-058: A correct provenance graph is an input assumption, not a solved capability
PACMI's benchmark supplies annotated dependency edges. It does not evaluate graph induction from raw text. Cascading invalidation may look reliable with oracle edges while failing under missing, noisy, or over-broad relations.

## C-059: Origin integrity is not truth
Authenticated origin binding can stop certain laundering paths from turning untrusted content into actionable authority. It cannot guarantee that a trusted source is accurate, current, or relevant. A trusted but stale or compromised source remains a risk.

## C-060: Provenance can be present yet malleable
A semantic derivation edge written or interpreted by an LLM can be dropped, misclassified, or made to appear trusted after summarization or tool echo. Security-critical origin should be bound by a trusted channel monitor and preserved across transformations; a model-generated lineage label alone is insufficient.

## C-061: Temporal consistency and semantic correctness are orthogonal
Bitemporal/transactional controls can make conflicting writes replayable and preserve the losing record. They do not ensure the chosen winner is true. Semantic adjudication needs evidence checks and may need to abstain.

## C-062: Invalidation can cause harmful overcorrection
A broad cascade may retire still-valid conclusions connected by association rather than logical dependency. Measure false invalidation and downstream benign regressions alongside missed invalidations and stale actions.

## C-063: Strong security results depend on monitor assumptions
Origin-bound authority's guarantees depend on correct write-time origin labels, authenticated channels, and genuinely independent trusted principals. Correlated sources, compromised trust registries, free-text answer bias, and untracked value-level flows remain relevant boundaries.

## C-064: The evidence ledger and execution ledger answer different questions
Execution influence is not evidential support. A message can affect a decision without making it more justified; a source can justify a claim without being the execution step that introduced it. Attribution systems must not conflate the two.

## Decisive follow-up
Run a factorial study varying temporal versioning, dependency propagation, origin binding, authorization gating, and evidence verification; vary graph quality and source correlation; measure both security outcomes and benign utility. Preserve null effects and report the individual component effects and interactions.
