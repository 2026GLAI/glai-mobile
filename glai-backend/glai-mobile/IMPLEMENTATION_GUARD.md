# IMPLEMENTATION_GUARD

## Purpose

This document protects the intent of GLAi v1 during implementation.

Its role is to prevent accidental or intentional distortion
of user trust, behavioral rules, and system philosophy
while writing code.

This document has higher priority than technical convenience.

---

## Core Principle

Implementation must obey intent.

If a technical solution conflicts with documented behavior,
the solution is wrong — even if it is elegant, efficient, or standard.

---

## What Developers Must Assume

Developers must assume:

- the documents describe *user reality*, not abstractions
- simplicity is a requirement, not a preference
- removing features is safer than adding them
- silence and restraint are valid system behaviors

---

## Forbidden Implementation Patterns

The following patterns are not allowed in v1:

- adding features “because users might want them”
- adding explanations not explicitly required
- adding UI elements to “improve engagement”
- optimizing for speed at the cost of clarity
- introducing hidden system states
- auto-correcting user intent without confirmation
- using dark patterns, nudges, or psychological hooks

---

## Trust Preservation Rule

If an implementation choice creates even a small risk
of confusing, pressuring, or misleading the user,
it must be rejected.

Trust is not a UX layer.
Trust is the system.

---

## Error Handling Constraint

All error handling must follow:

- ERROR_LANGUAGE.md
- FAILURE_HANDLING.md
- ERRORS_AND_FAILURES.md

No technical error may surface without being translated
into a human-safe, calm, and non-blaming response.

---

## State Integrity Rule

Implementation must respect SYSTEM_STATES.md exactly.

- Only one state may be active at a time
- State transitions must be explicit
- No background or implicit state changes
- Uncertainty is always safer than assumption

---

## UI Constraint

UI must:

- never require explanation
- never expose system mechanics
- never display options not strictly necessary
- never increase cognitive load

If a UI element needs justification,
it should not exist.

---

## Scope Enforcement

If a feature is not clearly supported by:

- LAUNCH_SCOPE.md
- FREEZE_v1.md

It does not belong in v1.

---

## Conflict Resolution Rule

In case of conflict between:

- speed vs clarity → choose clarity
- feature vs trust → choose trust
- automation vs consent → choose consent
- completeness vs calmness → choose calmness

---

## Final Guard Rule

If developers feel the urge to ask:
“Can we bend this rule just a little?”

The answer is no.

v1 exists to prove restraint.

End of Document
