# Current Synthesis — 2026-09-14

## Major conclusion change
The main unresolved bottleneck is no longer whether heterogeneous agents can exchange latent representations. Multiple 2026 results now support that capability. The harder problem is converting private specialist information into reliable distributed computation while preserving independence, controlling communication, preventing drift, and resisting common-mode or malicious latent failures.

## Claim status

| Claim | Current status | Reason |
|---|---|---|
| Modular specialist agents are useful | Established | Broad prior literature |
| Latent inter-agent communication is feasible | Strongly supported | Interlat and StateBridge |
| Latent communication is universally interoperable | Unsupported | Interfaces and model geometry remain dependent |
| Communication alone yields distributed computation | Contradicted/strongly challenged | SILO-BENCH and MAS-BENCH |
| More specialists imply more independent information | Unsupported | Diversity/representation collapse evidence |
| Diversity can improve collective reasoning | Partially supported | Depends strongly on selection quality |
| Adaptive communication control improves reliability | Promising/partially supported | Recent calibrated control evidence |
| Latent channels are safer/more auditable than text | Unsupported | Hidden-state integrity and inspectability problems |
| Hypernetworks can regenerate unique lost knowledge | Unproven | Generation is not information recovery |
| Full Cognitive Holobiont superiority | Unproven | No compute-matched end-to-end demonstration |

## New architectural requirement
Add an explicit communication-control and integrity layer between specialists and evidence fusion. Communication should be treated as a decision with expected information gain, cost, drift risk, redundancy, and common-mode risk rather than a fixed always-on protocol.

## Core experimental requirement
Any future Holobiont result must include matched baselines for a single model, MoE, ensemble, conventional MAS, latent MAS, and hybrid text/latent systems, with parameter/FLOP/memory/communication budgets reported. Agent count alone is not a meaningful scaling variable; effective independent information contribution must be measured.
