# IMPLEMENTATION_ORDER

## Purpose

This document defines the mandatory order of implementation for GLAi v1.

Its role is to prevent premature coding,
misplaced optimization,
and feature-first development
that would undermine trust and system integrity.

Order is not a preference.
Order is a constraint.

---

## Core Rule

Nothing may be implemented
until everything before it is complete and verified.

Skipping steps invalidates the implementation.

---

## Phase 0 — Preconditions

Before any code is written, verify:

- FREEZE_v1.md is present and unchanged
- IMPLEMENTATION_GUARD.md is understood by all developers
- TECH_STACK_LOCK.md is acknowledged
- AUDIT_v1 has passed

If any item is missing, implementation must not start.

---

## Phase 1 — System State Engine

Implement first:

- SYSTEM_STATES.md as explicit, inspectable logic
- single active state at any time
- explicit state transitions
- default to Uncertainty when unclear

No UI.
No AI.
No API.

Fail if:
- states are implicit
- transitions are inferred
- multiple states overlap

---

## Phase 2 — Session Lifecycle

Implement next:

- session creation
- session identification
- session termination
- session reset on failure

Constraints:

- one user → one session
- no long-term memory
- no cross-session behavior

Fail if:
- sessions persist unintentionally
- state leaks across sessions

---

## Phase 3 — API Boundary (Minimal)

Implement:

- exactly one endpoint
- one input: user message
- one output: system response + state (if needed)

Constraints:

- no optional parameters
- no feature flags
- no hidden modes

Fail if:
- a second endpoint appears
- client gains decision authority

---

## Phase 4 — AI Gateway (Controlled)

Implement:

- one AI provider
- controlled request formatting
- controlled response intake

Constraints:

- AI output is treated as untrusted
- AI never sets state
- AI never bypasses rules

Fail if:
- raw AI output reaches the user
- AI decides behavior

---

## Phase 5 — Rule Enforcement Layer

Implement:

- FIRST_RESPONSE_RULES
- STOP_RULES
- RESUME_RULES
- FAILURE_HANDLING
- ERROR_LANGUAGE

Constraints:

- rules override AI output
- silence and refusal are valid outcomes

Fail if:
- system responds when it should stop
- errors feel technical or blaming

---

## Phase 6 — Client (Mobile Web)

Implement last:

- text input
- response display
- loading and error states

Constraints:

- no logic
- no interpretation
- no optimization

Fail if:
- UI suggests actions
- UI explains itself

---

## Phase 7 — Human Validation

Before release:

- test with non-technical users
- observe without instruction
- document confusion points

Fail if:
- explanation is required
- users feel rushed or judged

---

## Implementation Completion Rule

Implementation is complete
when no developer feels the urge
to “add just one more thing”.

That urge is the signal to stop.

---

## Final Rule

If the order is broken,
trust will be broken later.

Follow the order.

End of Document
