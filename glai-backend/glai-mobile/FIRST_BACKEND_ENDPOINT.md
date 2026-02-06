# FIRST_BACKEND_ENDPOINT

## Purpose

This document defines the logical behavior of the first and only backend endpoint in GLAi v1.

It does not describe implementation details or code.
It defines responsibility, order, and constraints
for handling the very first user message.

This endpoint is the core interaction of the entire system.

---

## Endpoint Role

The endpoint exists to:

- receive one user message
- process it through system rules
- return one safe, human-level response

Nothing more.

---

## Input Definition

The endpoint accepts:

- one user message (text)
- minimal session identifier (if already established)
- optional language context

Constraints:

- input is always untrusted
- input meaning must not be altered
- no assumptions about user intent

If input is empty or unclear,
the system must default to Uncertainty.

---

## Processing Order (Mandatory)

The backend must process the request in this exact order:

1. Session validation or creation
2. State set to Listening
3. User input received
4. State transition to Understanding
5. Intent clarity check
6. State decision:
   - Responding
   - Uncertainty
   - Limitation
7. AI query (only if allowed by state)
8. Rule filtering and validation
9. Final state confirmation
10. Response delivery

Skipping or reordering steps is forbidden.

---

## State Authority

The endpoint is the sole authority for:

- determining the active system state
- transitioning between states
- enforcing state constraints

The client has no influence over state decisions.

---

## AI Interaction Constraint

AI may be queried only if:

- state is Responding
- rules allow a response
- no safety or trust rule blocks output

AI output:

- is treated as a draft
- may be modified or discarded
- may result in silence or refusal

AI never sets state.

---

## Response Definition

The endpoint returns:

- one textual response
- optional explicit state indicator (if required by UI)

Constraints:

- no metadata
- no reasoning chains
- no alternative answers
- no confidence markers

If no safe response exists,
a limitation or uncertainty message must be returned.

---

## Error Handling

All errors must:

- follow FAILURE_HANDLING.md
- use ERROR_LANGUAGE.md
- avoid technical explanations
- preserve user dignity

Errors are responses, not failures.

---

## Rate & Load Behavior

Under load or failure:

- behavior must degrade gracefully
- responses may slow, but not change meaning
- uncertainty is preferred over speed

The endpoint must never rush.

---

## Forbidden Behaviors

The endpoint must never:

- expose AI output directly
- explain system mechanics
- suggest next actions proactively
- collect additional data implicitly
- adapt behavior silently

---

## Completion Rule

The endpoint is correctly implemented
when its behavior can be fully explained
using only this document and SYSTEM_STATES.md.

If code requires explanation beyond this,
the implementation is wrong.

End of Document
