# IMPLEMENTATION_REVIEW_TEMPLATE

## Purpose

This document defines the formal review process
for accepting any implementation work in GLAi v1.

Its goal is to verify alignment with documented intent,
not to evaluate code quality, performance, or cleverness.

Implementation exists to serve documents.
Documents do not adapt to implementation.

---

## Review Scope

This review applies to:

- backend implementation
- client implementation
- infrastructure setup (if any)

Anything not covered by v1 documents
is out of scope and must be rejected.

---

## Review Rule

Implementation is accepted only if
**all checks below pass without exception**.

Partial acceptance is not permitted.

---

## Reviewer Position

The reviewer:

- does not need to read code
- does not need technical explanations
- does not negotiate intent

All answers must reference existing documents.

---

## Review Checklist

### 1. Document Alignment

Verify that:

- implementation follows FREEZE_v1.md
- IMPLEMENTATION_ORDER.md was respected
- TECH_STACK_LOCK.md was not violated

Reject if:
- work was done out of order
- undocumented changes exist

---

### 2. Behavioral Fidelity

Verify that:

- SYSTEM_STATES are implemented explicitly
- STATE_TRANSITION_TABLE is respected
- no implicit or shortcut transitions exist

Reject if:
- behavior differs under edge cases
- multiple states appear simultaneously

---

### 3. Endpoint Discipline

Verify that:

- exactly one backend endpoint exists
- input and output match FIRST_BACKEND_ENDPOINT.md
- API_BOUNDARIES are enforced

Reject if:
- extra parameters are accepted
- hidden modes or flags exist

---

### 4. AI Control

Verify that:

- AI output is always filtered
- AI never sets state
- AI behavior matches documented constraints

Reject if:
- raw AI output is exposed
- AI appears authoritative

---

### 5. Trust & Safety

Verify that:

- USER_TRUST rules override usefulness
- FAILURE_HANDLING behaves as documented
- ERROR_LANGUAGE is applied consistently

Reject if:
- system pressures the user
- errors feel technical or blaming

---

### 6. UI Minimalism (Client)

Verify that:

- UI matches SCREEN_01–03
- UI_LEVELS are respected
- no guidance or suggestions are added

Reject if:
- UI explains itself
- UI nudges user behavior

---

### 7. Language Behavior

Verify that:

- LANGUAGE_STRATEGY is implemented
- automatic language selection behaves correctly
- no broken characters or mixed languages appear

Reject if:
- language switching confuses the user

---

### 8. Performance Under Constraint

Verify that:

- system slows gracefully
- behavior does not change under load
- uncertainty is preferred over rushed responses

Reject if:
- system becomes erratic or misleading

---

### 9. Boundary Enforcement

Verify that:

- DATA_BOUNDARIES are respected
- SESSION_LIFECYCLE behaves correctly
- no cross-session influence exists

Reject if:
- data persists unintentionally
- sessions leak state

---

### 10. Human Validation

Verify that:

- a non-technical person can use the system unaided
- confusion points are acknowledged and fixed
- no explanation is required to proceed

Reject if:
- reviewer must explain how to use the system

---

## Review Outcome

### Accepted

All checks pass.
Implementation may proceed to release checks.

### Rejected

One or more checks fail.
Implementation must be corrected and re-reviewed.

No partial approval is allowed.

---

## Dispute Resolution Rule

If a developer disagrees with rejection:

- they must reference a document
- personal opinion is not valid
- undocumented behavior is invalid by default

Silence or ambiguity favors rejection.

---

## Final Rule

If accepting the implementation
requires trust in the developer,

the implementation is not acceptable.

Trust must be enforced by structure.

End of Document
