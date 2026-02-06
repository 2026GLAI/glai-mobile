# API_BOUNDARIES

## Purpose

This document defines the strict boundaries of the GLAi v1 API.

Its role is to prevent API expansion, leakage of system intent,
and coupling between components that would compromise trust,
clarity, or replaceability.

The API exists to serve behavior — not convenience.

---

## Core Principle

The API is not a product.
The API is a narrow conduit.

Every exposed capability increases risk.
Every unnecessary parameter weakens control.

---

## API Scope (v1)

GLAi v1 exposes exactly one functional interaction:

- submit a user message
- receive a system response

No other capabilities are permitted.

---

## Request Boundaries

### Allowed Input

The API may accept:

- a single user message
- minimal session identifiers
- language context (if available)

Constraints:

- input must be treated as untrusted
- no assumptions about intent
- no preprocessing that alters meaning

---

### Forbidden Input

The API must not accept:

- user profiles
- behavioral history
- preference data
- hidden flags or modes
- client-side state authority

If input cannot be explained to a user,
it must not exist.

---

## Response Boundaries

### Allowed Output

The API may return:

- one clear textual response
- explicit error or limitation messages
- explicit state indicators (if required by UI)

Constraints:

- no metadata exposed to the user
- no raw AI output
- no system internals

---

### Forbidden Output

The API must never return:

- confidence scores
- reasoning chains
- alternative answers
- system prompts
- debug or diagnostic data
- AI provider identifiers

Opacity protects trust.

---

## State Authority Rule

The backend API is the sole authority for:

- system state
- state transitions
- error classification
- response eligibility

The client may not infer, override, or simulate state.

---

## Versioning Discipline

API changes are tightly controlled:

- v1 endpoints are frozen
- additive changes are discouraged
- breaking changes require a new version

Backward compatibility is preferred over feature growth.

---

## Error Boundary Rule

All API errors must:

- map to defined failure categories
- follow ERROR_LANGUAGE.md
- avoid technical detail
- avoid blame

An API error is a user-facing moment of truth.

---

## Rate Limiting Boundary

Rate limiting must be:

- enforced server-side
- predictable
- transparent in effect

No silent throttling.
No deceptive degradation.

---

## Security Boundary

The API must:

- never expose secrets
- never trust client enforcement
- assume hostile or broken clients

Security is assumed to be imperfect elsewhere.
The API is the last line of defense.

---

## Observability Boundary

Internal logging and monitoring:

- must never affect API behavior
- must never alter responses
- must never leak externally

Observability serves maintenance, not adaptation.

---

## Forbidden API Patterns

The following are explicitly forbidden in v1:

- multiple endpoints for similar actions
- optional behavior flags
- “advanced” or “expert” modes
- hidden query parameters
- undocumented responses

Flexibility is postponed.

---

## Final Boundary Rule

If someone asks:
“Can we just add one more parameter?”

The answer is no.

GLAi v1 is defined by narrowness.

End of Document
