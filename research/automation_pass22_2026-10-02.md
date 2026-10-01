# Pass 22 — 2026-10-02

## Substantive update

This pass adds a stronger distributed-information failure result and changes the architecture question from "how much should agents share?" to "how can agents expose *unshared information* without premature convergence?"

### New evidence

1. **HiddenBench / ICML 2026:** 65 hidden-profile tasks across 15 frontier LLMs found 30.1% collective accuracy when information was distributed, versus 80.7% for a single agent given the complete information. The reported bottleneck is not simply message bandwidth: agents often fail to recognize latent information asymmetry—what another agent may know but has not yet said—and converge on shared evidence. A lightweight structured communication protocol improved performance. This is highly relevant to the Holobiont hypothesis because it directly tests complementary private information.
2. **SILO-BENCH / ACL 2026:** 30 algorithmic tasks, 54 configurations and 1,620 experiments similarly isolate an integration bottleneck: agents communicate and form useful topologies but often cannot synthesize distributed state, with coordination overhead worsening at scale.
3. **DeLM (2026):** a competing design uses asynchronous workers, a task queue, and a shared verified context. Reported SWE-bench Verified and LongBench-v2 gains show that a shared-state architecture can solve some coordination problems without conventional central orchestration.
4. **Interaction Tax / ICML 2026:** matched-budget optimization experiments show that full-solution exchange can erase useful diversity between model families, while independent proposals preserve coverage. Thus "share more" is not a defensible default.
5. **Adaptive topology work:** AGP, TopoDIM, DyTopo and GoAgent provide convergent evidence that task-dependent topology and selective/group-level communication can improve performance or token efficiency, but these are not yet causal evidence for Holobiont-level synergy.

## Revised synthesis

The evidence now supports a more specific hypothesis:

> **The critical capability is active elicitation and integration of complementary private information while preserving useful independence.**

This is stronger than the earlier "staged coupling" statement because it identifies the missing capability exposed by HiddenBench: agents must reason about *information asymmetry itself*, not merely route messages.

A promising architecture therefore separates:
- independent exploration;
- epistemic metadata / information-need declarations;
- targeted elicitation of unshared evidence;
- verified shared-state admission;
- independent challenge;
- final integration.

## Important contradiction

DeLM demonstrates that a shared verified context can be effective, so private point-to-point routing is not a prerequisite. The Holobiont must therefore beat or complement shared-state coordination under matched compute, bandwidth, verification, memory, and information budgets.

## Falsification consequence

A Holobiont claim fails if its advantage disappears after:
- giving a single agent the union of information at matched reasoning budget;
- matching total communication and verification;
- comparing against independent sampling + selection;
- comparing against verified shared context;
- permuting private-information ownership;
- ablating the information-need/elicitation mechanism.

A positive result is only interesting if the gain is attributable to causal integration of complementary information rather than extra compute, extra information, or better verification.

## Status

The core Holobiont-level synergy claim remains **unvalidated**. Evidence for adaptive coordination/control is stronger than evidence for new collective computational capability.

## Sources

- https://proceedings.mlr.press/v306/li26ej.html
- https://aclanthology.org/2026.acl-long.1354/
- https://arxiv.org/abs/2606.10662
- https://arxiv.org/abs/2608.23541
- https://journals.sagepub.com/doi/10.3233/FAIA251326
- https://aclanthology.org/2026.findings-acl.207/
- https://arxiv.org/abs/2603.19677
- https://arxiv.org/abs/2602.06039
