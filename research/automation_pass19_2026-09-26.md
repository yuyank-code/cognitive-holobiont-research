# Cognitive Holobiont Research — Pass 19 (2026-09-26)

## Executive finding

This pass sharpens the central hypothesis: the Holobiont must exploit complementary private information while preventing premature global dependence. The originating PDF remains a hypothesis/specification, not established fact.

SILO-BENCH remains a strong negative control: active communication can fail to become distributed computation. DeLM is a serious competing architecture: asynchronous agents using verified shared context and a task queue can improve coordination. Diversity-collapse work shows dense interaction can reduce useful independence. Topology-generation work makes communication structure a controllable variable, but does not yet prove causal collective computation.

## Literature updates

- SILO-BENCH: ACL 2026; 30 exact algorithmic tasks, 54 configurations and 1,620 experiments. It reports a communication-reasoning gap and severe scaling failure on complex tasks. https://aclanthology.org/2026.acl-long.1354/
- DeLM: decentralized asynchronous agents with verified shared context and a task queue; reported gains on SWE-bench Verified and LongBench-v2. The gain is not yet causally decomposed into decentralization, verification, decomposition, or additional search. https://arxiv.org/abs/2606.10662
- TopoDIM: one-shot heterogeneous communication topology; reports lower token use and modest performance improvement. Topology intervention remains necessary to establish causality. https://aclanthology.org/2026.findings-acl.207/
- Diversity Collapse: dense interaction can accelerate premature convergence and group-size scaling has diminishing returns. https://aclanthology.org/2026.findings-acl.13/
- Emergent Coordination: PID/TDMI offers a measurement language for unique, redundant and synergistic interaction contributions, but its demonstrated task is not exact distributed computation. https://arxiv.org/abs/2510.05174

## Supporting evidence

Adaptive communication control, verified shared state, dynamic topology, and information decomposition all strengthen the control-layer hypothesis.

## Contradictory or limiting evidence

Active communication can fail at integration; dense coupling can destroy diversity; shared verified context may reproduce practical gains without a special private-information mechanism; multi-agent gains can be confounded by extra inference, verification, or decomposition quality.

## Revised mathematical framing

Let agents hold private evidence X_1,...,X_n, shared state S, target Y, and action history A. Define an operational dependence cost D_i as the change in other agents' behavior attributable to exposing X_i, estimated through a withholding counterfactual. Define unique task value U_i = I(Y;X_i | S,X_-i^obs). Define coalition synergy operationally as the performance residual that remains after matching compute and evidence access against the best proper subset.

A scheduler objective should trade task-relevant coalition gain against bandwidth, latency, induced dependence, correlated-failure risk and governance cost:

J = Gamma - lambda_B B - lambda_T T - lambda_D D - lambda_F F - lambda_G G.

These quantities are research constructs, not established laws.

## Falsification framework

A convincing positive result must partition private evidence, permute ownership, ablate an information owner, substitute/randomize its message while preserving surface statistics, match total inference and verifier calls, match evidence access, intervene on topology, measure pre/post dependence and diversity, inject noisy/adversarial agents, and replicate across task families.

Reject the strong hypothesis if the gain disappears after resource matching, sender ablation has no causal effect, or a verified shared-context baseline reproduces the gain without the proposed private-information mechanism.

## Architecture conclusion

heterogeneous private specialists -> epistemic-state estimation -> dependence-aware scheduler -> private routing / verified shared context -> sparse adaptive topology -> causal communication -> provenance/authorization/privacy -> dependency-aware integration -> independent verification -> termination -> governed memory -> bounded repair -> validation-gated reconfiguration

The new architectural requirement is explicit: measure and control dependence, not merely information flow.

## Bottom line

Pass 19 does not validate the Holobiont hypothesis. It makes the hypothesis harder to fake. The key scientific object is causal, task-relevant coalition synergy under controlled information ownership and controlled induced dependence. No implementation is justified yet.
