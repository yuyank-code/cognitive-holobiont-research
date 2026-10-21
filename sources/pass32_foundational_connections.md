# Pass 32 Foundational Connections

- W3C PROV-DM (2013 Recommendation): provenance models entities, activities, agents, derivations, and time. Provenance is a representation of asserted lineage; it does not certify factual truth.
- PostgreSQL 16 transaction-isolation documentation, §13.2: Serializable transactions are equivalent to some serial order of committed transactions, but applications must handle serialization failures and retry. This is a consistency guarantee for writes, not a guarantee that the data or semantic decision is true.
- These foundations support a strict separation between provenance/lineage, transaction consistency, epistemic support, and temporal applicability in the Holobiont research model.