# Automation Pass 15 — 2026-09-22

## Research focus

This pass tested whether the information-market / epistemic-coordination formulation survives newer evidence on interaction cost, diversity collapse, coalition stability, constraint drift, and adaptive information acquisition.

The originating treatise remains a hypothesis/specification. No component-level result is treated as validation of the whole architecture.

## New evidence

### 1. Interaction has a measurable tax

Ann, Liu & Tan (2026), *The Interaction Tax*, reports 11 matched-budget optimization tasks in which full-solution interaction can erase diversity that independent proposals preserve. The result is directly relevant to the Holobiont claim that communication should be selective rather than default-broadcast. The useful variable is therefore not communication volume but information selected for transmission and its timing.

Source: https://arxiv.org/abs/2608.23541

### 2. Diversity collapse is structural, not merely model weakness

Chen et al. (2026), *Diversity Collapse in Multi-Agent LLM Systems*, reports diminishing returns with group size and faster premature convergence under dense communication. This supports treating epistemic independence as a consumable architectural resource.

Source: https://arxiv.org/abs/2604.18005

### 3. Selective disagreement retention is a plausible countermeasure

Nguyen et al. (2026), *Hear Both Sides*, reports gains from retaining messages that maximize disagreement rather than broadcasting all responses. This is supporting evidence for a selective-information controller, but it is not evidence of distributed computation because the tasks are still aggregate reasoning/debate benchmarks.

Source: https://arxiv.org/abs/2603.20640

### 4. Coalition formation introduces a strategic layer

Guo, Wu & Yiu (2026), *Coalition Formation in LLM Agent Networks*, models dynamic coalitions with hedonic-game concepts and reports empirical stability under a specific protocol. This suggests that topology formation should not be modeled only as an information-routing problem: agent preferences, coalition incentives, and stability can change which information channels exist.

Source: https://arxiv.org/abs/2604.14386

### 5. Constraint drift creates a second state that must survive communication

Li et al. (2026), *Constraint Drift in LLM-Based Multi-Agent Systems*, argues that safety constraints can weaken as execution passes through delegation, memory, communication, and tool use. This is important for the Holobiont because an information-optimal routing policy could otherwise select a channel that violates provenance, privacy, or authority constraints.

Source: https://arxiv.org/abs/2605.10481

### 6. Secret channels can create collusion modes

Nakamura et al. (2026), *Colosseum*, audits cooperative MAS for collusion using a DCOP formulation and finds that secret communication channels can produce collusive behavior in many tested out-of-the-box models. This is contradictory evidence against treating latent/private channels as automatically beneficial. Hidden channels need explicit governance and auditability.

Source: https://arxiv.org/abs/2602.15198

### 7. Value-of-information formalism supports active querying

Dong et al. (2026), *Value of Information: A Framework for Human-Agent Communication*, provides a decision-theoretic basis for querying when expected utility gain exceeds interaction cost. Although the setting is human-agent communication, the same structure transfers naturally to specialist-to-specialist requests.

Source: https://arxiv.org/abs/2601.06407

## Revised synthesis

The information-market hypothesis must be expanded. A message is not valuable merely because it carries conditional information. It is valuable only if its expected decision/computation benefit survives four filters:

1. epistemic value — unique or synergistic information not already available;
2. interaction cost — bandwidth, latency, compute, and attention;
3. coupling cost — risk of convergence, correlated failure, or loss of independent search;
4. governance cost — provenance, privacy, authority, safety, and collusion risk.

This makes selective communication a constrained control problem rather than a simple auction over information gain.

## Architectural consequence

The communication controller should preserve independent local hypotheses until there is positive expected value in coupling. It should be able to request information, reject information, quarantine a channel, preserve disagreement, or terminate interaction.

A hub/market mechanism is therefore not sufficient by itself. The system requires a **governed epistemic scheduler** whose objective is task utility subject to independence, provenance, safety, and fault constraints.

## What this pass does NOT establish

- It does not establish positive coalition synergy over matched centralized baselines.
- It does not establish that latent communication is superior to carefully selected text communication.
- It does not establish that adaptive topology improves exact distributed computation.
- It does not establish consciousness, biological equivalence, or open-ended self-rearchitecture.

## Current confidence

The strongest supported claim is now narrow: selective, context-dependent communication is more defensible than unrestricted broadcast, and communication should be treated as a resource allocation problem under epistemic and governance constraints. The genuinely novel Holobiont claim remains unvalidated until exact distributed-computation experiments demonstrate positive coalition synergy under matched resources.
