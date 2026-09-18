# Contradictions — Pass 12 Addendum — 2026-09-19

### C-058 Decentralization gains may be infrastructure gains
DeLM improves reported performance using shared verified context, asynchronous task queues and decomposition. The gain cannot yet be attributed uniquely to decentralization. A centralized system with the same state, verification and decomposition budget could potentially reproduce part or all of it.

### C-059 Adaptive topology can trade communication efficiency for controller dependence
DyTopo/GoAgent/RAPS show benefits from changing topology, but the mechanism choosing edges/groups can become a common-mode failure. The topology controller must therefore be included in fault-injection and matched-compute accounting.

### C-060 Shared verified state can amplify verification errors
A shared context reduces repeated integration, but an incorrect verification rule or corrupted state can propagate to many agents. Replication of state is not equivalent to independent verification.

### C-061 Individual communication quality can be anti-predictive of collective success
CRAFT shows that stronger private reasoning/public communication scores do not reliably predict collaborative performance. This directly challenges proxy metrics that score agents independently and then assume collective competence.

### C-062 Metamorphic testing is not a complete oracle
MORPHAGENT can detect many seeded coordination and goal-deviation faults, but the strength of the result depends on the chosen metamorphic invariants. A system can satisfy process invariants while still producing a semantically wrong answer.
