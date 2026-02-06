# GLAi v1 — Traceability Map

This document binds backend implementation to the authoritative
documentation in `glai-mobile`.

Documents override code.
Behavior is not inferred.
Only explicit mappings are allowed.

---

## Authority Source

UX, behavior, language, and limits are defined in:
`glai-mobile/INDEX.md`

Backend implementation MUST comply with:
- AUDIT_v1.md
- FREEZE_v1.md

---

## Core Behavior Mapping

### System States
- Source: glai-mobile/SYSTEM_STATES.md
- Backend: State engine (authoritative, server-side)
- Rule: No implicit or blended states

### State Transitions
- Source: glai-mobile/STATE_TRANSITION_TABLE.md
- Backend: Explicit transition table
- Rule: Invalid transitions are rejected

---

## Response Rules

### First Response
- Source: glai-mobile/FIRST_RESPONSE_RULES.md
- Backend: Applied on session start
- Rule: No task execution before acknowledgment

### Stop / Resume
- Source:
  - STOP_RULES.md
  - RESUME_RULES.md
- Backend: Session control endpoints
- Rule: User intent overrides momentum

---

## Failure & Safety

### Failure Handling
- Source: FAILURE_HANDLING.md
- Backend: Central error handler
- Rule: Calm, non-judgmental responses only

### Error Language
- Source: ERROR_LANGUAGE.md
- Backend: Error message templates
- Rule: No blame, no pressure

### Trust
- Source: USER_TRUST.md
- Backend: Global constraint
- Rule: Trust overrides usefulness

---

## UI-Driven Constraints (Server-Enforced)

### Screens & Flow
- Source:
  - SCREEN_01.md
  - SCREEN_02.md
  - SCREEN_03.md
  - NAVIGATION_FLOW.md
- Backend: Allowed action set per state
- Rule: Server rejects forbidden actions

---

## Language & Context

### Language Strategy
- Source: LANGUAGE_STRATEGY.md
- Backend: Response formatter
- Rule: Tone never authoritative

### Context Modes
- Source:
  - TOURIST_MODE.md
  - GOVERNMENT_FRIENDLY.md
- Backend: Mode flag (non-behavioral)
- Rule: Mode does not change intent

---

## Architecture & API

### API Boundaries
- Source: API_BOUNDARIES.md
- Backend: Endpoint surface
- Rule: No hidden inputs or outputs

### Session Lifecycle
- Source: SESSION_LIFECYCLE.md
- Backend: Session manager
- Rule: Server holds authority

---

## Scope & Release

### Launch Scope
- Source: LAUNCH_SCOPE.md
- Backend: Feature flags
- Rule: Anything outside scope is disabled

---

## Implementation Guard

- Source: IMPLEMENTATION_GUARD.md
- Backend: Mandatory review gate
- Rule: No interpretation allowed

---

## Final Rule

If backend behavior cannot be traced to a document,
it must not exist in GLAi v1.

End of Document
