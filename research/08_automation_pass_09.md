# Automation Research Pass 09 — 2026-09-17

## Research focus
Follow-up on the two highest-risk bottlenecks: heterogeneous latent interoperability and conversion of distributed information into reliable computation. Search emphasis was 2026 primary/open literature and direct negative evidence.

## New evidence

### 1. Heterogeneous latent communication is moving from feasibility toward information-structure analysis
Interlat (ACL 2026) reports latent communication across heterogeneous models and positions itself as a feasibility study. A June 2026 preprint, *See What I See, Know What I Think: Dense Latent Communication Across Heterogeneous Agents*, extends this direction to heterogeneous Qwen3 model sizes and explicitly separates context-aware from context-unaware transfer. Its key result is an information-structure duality: when the receiver already has the input, transferable reasoning signals can be sparse; when the receiver lacks the context, useful transfer requires preserving much denser contextual knowledge. The system uses learned cross-model KV alignment rather than assuming raw hidden-state compatibility.

**Implication:** the Holobiont should model a message as a conditional information channel whose utility depends on receiver context. “Latent bandwidth” and “semantic richness” are not sufficient measures.

### 2. Distributed computation remains the decisive negative frontier
SILO-BENCH (ACL 2026) evaluates 1,620 configurations across 30 exact algorithmic tasks and reports a communication-reasoning gap: agents communicate actively but fail to turn interaction into effective distributed computation; the hardest global-shuffle tasks reach zero success beyond 50 agents. MAS-BENCH independently reports sharp degradation in distributed sorting as agent count rises, with failures in shared state, convention alignment and termination. These results converge on the same bottleneck from different task designs.

**Implication:** a Holobiont paper cannot claim collective cognition from communication gains alone. It needs exact distributed tasks in which each specialist possesses indispensable private information and the system must compose it.

### 3. Selection is a separate bottleneck from generation
The Selection Bottleneck study reports that selection-based aggregation can substantially outperform synthesis-based aggregation and that independent evaluation can attenuate headline diversity gains. This supports separating generator quality/diversity from the mechanism that decides which information survives.

**Implication:** the architecture needs an explicit integration/selection layer with independent evaluation and dependency-aware provenance.

### 4. Self-healing evidence remains bounded
The 2026 Scientific Reports SHNN paper demonstrates modular patch-based recovery after structural/adversarial damage on small image benchmarks. This strengthens the claim that neural behavior can be repaired without global retraining, but it does not demonstrate recovery of unique learned knowledge after all copies of that knowledge are destroyed.

**Implication:** distinguish repair of computation from resurrection of information. The latter remains an information-theoretic problem.

## Revised conceptual model

The current Holobiont research target is best represented as:

**private specialist states → capability-aware routing → context-conditional latent interface → integrity/provenance → information acquisition/request → distributed computation → dependency-aware selection → task anchoring/termination → distributed capability traces → repair → validation-gated reconfiguration**

This is narrower than the original treatise and scientifically stronger.

## Mathematical update

Let sender state be M_i, receiver-private context be X_R, task target be Y, and receiver baseline state be Z_R. Define conditional sender information:

`I_sender = I(Y ; M_i | X_R, Z_R)`

and causal communication utility:

`DeltaU_i = E[U(Y_hat | do(M_i)) - U(Y_hat | do(M_i = null))]`.

For context-aware latent transfer, the useful payload may be mostly a sparse incremental signal because X_R already explains much of Y. For context-unaware transfer, the payload must carry information about the missing context as well. Therefore communication evaluation should report both `I_sender` and `DeltaU_i`, not raw latent dimension or compression ratio.

For distributed computation, define a matched centralized baseline B with the same total input information and comparable compute/bandwidth budget. The central hypothesis is not simply `U_H > U_B`, but that the advantage survives removal of communication-independent factors and is concentrated on tasks where information is physically distributed. A stronger test is:

`Gain = U_H - U_B` with controls for total information, total inference FLOPs, memory, number of independent models, and transmitted bits/latent elements.

## Contradictions strengthened

- Successful heterogeneous latent transfer does not imply a universal latent language; current systems depend on learned alignment or constrained model families.
- High communication density can coexist with zero distributed-computation success.
- More agents can reduce reliability because coordination, shared-state consistency and termination costs grow faster than useful independent information.
- Repair mechanisms can restore a function while still failing the stronger requirement of recovering a destroyed unique capability.

## Highest-priority next frontier

1. Build a formal benchmark where sender-private facts are indispensable and receiver context is independently controlled.
2. Replicate latent causal-transfer tests across non-Qwen families and architectures.
3. Measure capability regret from routing errors rather than route accuracy alone.
4. Compare Holobiont-style distributed computation against large-context single models, MoE, shared-backbone adapters, text-MAS, latent-MAS and structured shared-state systems under matched budgets.
5. Introduce controlled correlated failures to determine whether effective independent channels predict resilience better than raw agent count.
