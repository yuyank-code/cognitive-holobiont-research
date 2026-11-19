# Mathematics Addendum — Pass 34: Communication Reliability and Evidence-Path Diversity

## 1. Model the information dependency graph

Let G=(V,E) be the organ and communication graph. An edge e in E transports a message, but each evidence item also has a source and ancestry. For evidence item z, define:

- s(z): originating sensor, model, database or external source;
- A(z): ancestry set of prior messages, transformations and memory records;
- t(z): creation time;
- V(z): validity interval or temporal scope;
- v(z): schema and codec version;
- a(z): authorization/provenance status;
- c(z): completeness status.

A receiver should not treat successful delivery as admissibility. A minimal admissibility predicate is:

Admit(z, task) = Complete(z) AND Authorized(z) AND Fresh(z, task) AND Traceable(z) AND SchemaCompatible(z).

Factual correctness remains a separate question; provenance and schema validity do not prove truth.

## 2. Route redundancy versus evidence redundancy

Let P(v,d) be the set of paths from an information origin to decision node d.

Route redundancy:
R_route(d) = number of edge-disjoint paths in P(v,d).

Evidence redundancy:
R_evidence(d) = number of sufficiently independent source lineages that can provide admissible support to d.

A system may have R_route > 1 but R_evidence = 1 when all paths copy the same upstream message.

Define an evidence-dependency cut:
K_evidence(d) = minimum number of independent source/failure domains whose removal disconnects all admissible evidence from d.

This is a conceptual metric until source dependence can be estimated. Shared base models, training corpora, retrieval stores, sensors, hypernetworks and codecs must be included in the failure-domain model.

## 3. Silent failure and detection

For injected fault F=f:

SFR(f) = P(final task failure AND no immediate detection | F=f).

Also report:
- P(detection | f);
- P(propagation | f);
- P(recovery | f);
- P(false recovery | f);
- time-to-detection and time-to-recovery.

Do not merge these into one reliability score. A system may detect a fault but fail to recover; it may recover the task outcome while retaining a corrupted memory record.

## 4. Evidence availability and recovery

Let Z_d be the set of admissible evidence items available to decision node d after fault f.

A_e(f) = 1 if at least one sufficient admissible evidence set remains, else 0.

R_s(f) = P(validated task recovery | f).

F_r(f) = P(system declares recovery AND held-out evidence/task contract fails | f).

The existence of an alternate path is not sufficient; the path must deliver a sufficient and admissible evidence set.

## 5. Selective routing as a constrained information allocation

Let M be shared memory, O_i the role/task context of organ i, and B_i its token budget. A routing policy pi chooses subset M_i:

M_i = pi(M, O_i, task_stage, B_i, risk).

Optimize task utility and reliability subject to communication and privacy constraints:

max_pi E[U_task] - lambda_t Tokens(pi) - lambda_l Latency(pi) - lambda_r Risk(pi)

subject to:
- required evidence is not omitted;
- authorization and privacy constraints are satisfied;
- critical evidence has a provenance path;
- verification budget is respected.

This makes the omission risk explicit. Selective routing is not automatically safe; false-negative memory selection must be measured.

## 6. Adaptive message format

Let formats be F={typed_graph, natural_language, latent_bridge, structured_memory}. For task context x, choose:

f*(x) = argmax_f E[U_task | x,f] - Cost(f) - Risk(f).

The router must be evaluated on held-out task types. A latent bridge should be compared to a typed/hybrid baseline at equal information, compute, latency and verifier budgets.

## 7. Causal repair

Let trace tau be an execution and a an intervention anchor. Replay the prefix tau[0:a] from recorded state; regenerate only the downstream suffix. Define:

RepairRate = P(held-out contract passes after intervention | reproducible fault).

ReproductionRate = P(same failure recurs when replaying without intervention).

A retry that succeeds without reproducing the failure is not sufficient evidence of causal repair.

## 8. Resource vector

For each architecture, report:

B = (C_train, C_infer, M, BW, L, I, V, P)

where C_train is training compute, C_infer inference compute, M memory, BW bandwidth, L latency, I information access, V verifier budget, and P provenance/recording overhead.

Claims of Holobiont advantage must compare Pareto frontiers under matched or explicitly normalized budgets.
