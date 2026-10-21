# Claim–Evidence Matrix Addendum — Pass 32
Date: 2026-10-22

| Claim | New evidence | Counterevidence / limitation | Status after Pass 32 |
|---|---|---|---|
| Memory should preserve temporal validity and historical facts separately | PACMI models supersession with a provenance graph and validity states; TOKI uses bitemporal writes and audit rows; STALE measures implicit conflict and downstream policy adaptation | PACMI uses annotated dependency edges, one update per case, a fixed short graph, and limited diagnostic queries; TOKI's end-task superiority evidence is explicitly underpowered | Strong design rationale; broad end-to-end benefit remains unproven |
| Cascading invalidation improves long-horizon task utility | PACMI's ablation raises answer errors from 3 to 11 when propagation is removed | The paired final-answer difference is not statistically significant at 0.05; benchmark graph is supplied; graph induction and noisy dependencies are unresolved | Mechanism promising; task-utility effect uncertain |
| Provenance/lineage is sufficient to prevent memory poisoning | Origin-bound authority work identifies self-summary, trusted-tool echo, and manufactured corroboration as laundering routes | A derivation edge can be lost or falsely elevated; origin-bound results depend on correct trusted write-time labels and independence assumptions | Claim rejected as stated; lineage needs non-malleable origin integrity and action policy |
| Authenticated origin proves factual truth | Origin-bound authority can gate consequential actions based on origin and authorization | An authenticated source can still be wrong, stale, compromised, or irrelevant | Unsupported; origin integrity and epistemic support must remain separate |
| Bitemporal consistency ensures semantically correct memory | TOKI formalizes write-time isolation, versioning, and audit behavior | A consistently committed adjudication can still be semantically wrong; natural workload comparison is limited | Supported only for the specified transaction contract, not semantic truth |
| Execution traces establish evidential support or causal contribution | Recent provenance survey distinguishes execution influence from evidence-support relations | Full-chain benchmarks and tamper-evident/attested trace evaluations are missing in surveyed work | Partially supported as an observability mechanism; not proof by itself |
| Combined memory governance and adaptive collaboration yields Holobiont-specific synergy | Components plausibly address complementary failure modes | No end-to-end factorial evaluation against matched simpler systems; added complexity and correlated errors may dominate | Unvalidated hypothesis |

## Update rule

Do not raise confidence because multiple preprints reuse similar assumptions or cite one another. Record independent replication separately from repeated claims within one research cluster. The origin-bound-authority, PACMI, and TOKI papers are preprints with distinct threat models and evaluation boundaries.
