# TECH_STACK

## Purpose

This document defines the minimal, acceptable technology stack for GLAi v1.

The goal is not innovation, scalability, or technical elegance.
The goal is reliability, clarity, and controllability.

Every technology choice must support trust, simplicity, and restraint.

---

## Core Principle

Boring technology is a feature.

If a technology requires explanation,
it does not belong in v1.

---

## Client (Mobile)

### Target

- Mobile-first
- Touch-first
- Text-first

### Acceptable Approaches

- Responsive web application (PWA)
- Thin native wrapper over web view (optional)

### Forbidden

- Platform-specific logic divergence
- Complex gestures
- Hidden interactions
- Heavy animations
- Gamification elements

The client must be replaceable without affecting system behavior.

---

## Frontend Stack (Minimal)

Allowed:

- HTML
- CSS
- Minimal JavaScript or TypeScript
- One lightweight UI framework (optional)

Requirements:

- Predictable rendering
- Explicit state handling
- No magic abstractions
- Easy inspection and debugging

Forbidden:

- Experimental UI frameworks
- Heavy state machines in the UI
- Client-side decision-making about user intent

The frontend does not think.
It displays and forwards.

---

## Backend

### Role

The backend is the source of truth for:

- system state
- behavior rules
- response orchestration

### Acceptable Characteristics

- Stateless or explicitly state-managed
- Clear request/response boundaries
- Deterministic behavior

Forbidden:

- Hidden heuristics
- Adaptive behavior without documentation
- Silent retries that change outcomes

---

## AI Integration

### Rules

- AI is accessed only through a controlled interface
- All AI outputs are treated as untrusted until validated by rules
- No direct exposure of raw AI responses to the user

AI does not decide behavior.
Documents do.

---

## State Management

System state must:

- live server-side
- be explicit
- be inspectable
- map directly to SYSTEM_STATES.md

No inferred states.
No blended states.
No background transitions.

---

## Data Storage

### Allowed

- Minimal session storage
- Explicit user data only when necessary

### Forbidden

- Long-term user profiling
- Behavioral analytics beyond reliability metrics
- Training data derived from user sessions (v1)

If data is not required for trust or function,
it must not be stored.

---

## Observability

Allowed:

- Basic logging
- Error tracking
- Health checks

Forbidden:

- User behavior optimization metrics
- Engagement scoring
- Attention tracking

Observability exists to detect failure, not to optimize humans.

---

## Security

Security must follow SECURITY_MODEL.md exactly.

Defaults:

- secure by default
- minimal surface area
- no optional security features

If security adds friction,
reduce features — not protection.

---

## Dependency Rule

Every dependency must justify its existence.

If removing a dependency does not break trust,
it should be removed.

---

## Versioning Constraint

v1 is frozen by FREEZE_v1.md.

No technology upgrade is allowed
unless it fixes a clear bug or security risk.

---

## Final Stack Rule

If the stack feels impressive,
it is wrong.

v1 should feel quiet, stable, and unsurprising.

End of Document
