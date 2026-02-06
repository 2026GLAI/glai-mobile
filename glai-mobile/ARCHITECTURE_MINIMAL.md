# ARCHITECTURE_MINIMAL

## Purpose

This document defines the minimal architectural shape of GLAi v1.

Its role is not to describe how to build everything,
but to define how little is enough.

Architecture exists to support behavior and trust —
not to demonstrate technical capability.

---

## Core Architectural Rule

GLAi v1 has only what it must have.

If an architectural element is not strictly required
to deliver a correct, calm, and trustworthy response,
it must not exist.

---

## High-Level Structure

GLAi v1 consists of exactly three components:

1. Client (Mobile Web)
2. Backend Gateway
3. External AI Provider

No additional components are allowed at v1.

---

## Component Responsibilities

### 1. Client (Mobile Web)

Responsibilities:

- collect user input
- display system output
- show loading and failure states

Constraints:

- no decision-making
- no behavioral logic
- no interpretation of user intent
- no persistence beyond session scope

The client is a window, not a brain.

---

### 2. Backend Gateway

Responsibilities:

- enforce system states
- apply behavioral rules
- manage session lifecycle
- control AI interaction
- protect secrets and limits

Constraints:

- minimal logic
- explicit flows
- predictable outcomes
- no learning behavior

The backend is the spine of the system.

---

### 3. External AI Provider

Responsibilities:

- generate candidate responses

Constraints:

- treated as non-authoritative
- never exposed directly to the user
- always filtered by system rules

AI is a tool, not a system component.

---

## Data Flow Constraint

All data flow must be:

- unidirectional
- explicit
- traceable

Client → Backend → AI  
AI → Backend → Client

No shortcuts.
No hidden channels.

---

## State Flow Constraint

System state transitions must:

- occur only in the backend
- be explicit
- map directly to SYSTEM_STATES.md
- be observable for debugging

No implicit or inferred state changes are allowed.

---

## Failure Containment

Failures must be contained at their origin.

- client failures do not affect backend state
- AI failures do not corrupt session logic
- backend failures must degrade gracefully

Cascading failure is considered a design error.

---

## Scalability Non-Goal

GLAi v1 is not designed to scale automatically.

Scaling is postponed until:

- behavior is proven
- trust is stable
- failure modes are understood

Architecture must not anticipate growth.

---

## Replaceability Rule

Each component must be replaceable
without requiring changes to the others.

If replacing a component requires system-wide changes,
the architecture is too tight.

---

## Forbidden Architectural Patterns

The following are explicitly forbidden in v1:

- microservices
- event-driven pipelines
- background workers
- message queues
- caching layers that affect behavior
- auto-scaling systems
- multi-region deployments

These patterns increase fragility without increasing trust.

---

## Architectural Integrity Rule

If an architectural decision conflicts with:

- SYSTEM_STATES.md
- IMPLEMENTATION_GUARD.md
- FREEZE_v1.md

The decision is invalid.

---

## Final Rule

If the architecture diagram cannot be explained
in under one minute to a non-technical person,
it is too complex for v1.

End of Document
