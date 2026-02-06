# GLAi v1 — Index

## Purpose

This index provides a complete, authoritative map
of the GLAi v1 documentation set.

It defines how documents relate to each other,
in what order they should be read,
and which documents have decision authority.

This repository is not a knowledge base.
It is a locked system definition.

---

## Reading Order (Recommended)

1. CORE.md  
2. VOICE.md  
3. ARCHITECTURE.md  
4. DECISIONS.md  

These documents define intent and tone.

---

## Behavioral Foundation

- SYSTEM_STATES.md  
- STATE_TRANSITION_TABLE.md  
- FIRST_RESPONSE_RULES.md  
- STOP_RULES.md  
- RESUME_RULES.md  
- FAILURE_HANDLING.md  
- ERROR_LANGUAGE.md  
- USER_TRUST.md  

These documents define how GLAi is allowed to behave.

---

## User Experience (Mobile-First)

- SCREEN_01.md  
- SCREEN_02.md  
- SCREEN_03.md  
- UI_LEVELS.md  
- NAVIGATION_FLOW.md  
- ONBOARDING_MINIMAL.md  

These documents define what the user sees and feels.

---

## Language & Context

- LANGUAGE_STRATEGY.md  
- TOURIST_MODE.md  
- GOVERNMENT_FRIENDLY.md  

These documents define how GLAi adapts to users
without changing behavior or intent.

---

## Architecture & Boundaries

- ARCHITECTURE_MINIMAL.md  
- API_BOUNDARIES.md  
- DATA_BOUNDARIES.md  
- SESSION_LIFECYCLE.md  
- SECURITY_MODEL.md  
- SYSTEM_RESILIENCE.md  

These documents define structural and safety limits.

---

## Platform & Strategy

- PLATFORM_DECISION.md  
- TECH_STACK.md  
- TECH_STACK_LOCK.md  

These documents define where and how GLAi exists technically.

---

## Implementation Control

- IMPLEMENTATION_GUARD.md  
- IMPLEMENTATION_ORDER.md  
- FIRST_BACKEND_ENDPOINT.md  
- BACKEND_ACCEPTANCE_TESTS.md  
- IMPLEMENTATION_REVIEW_TEMPLATE.md  

These documents define how implementation is allowed to proceed
and how it is evaluated.

---

## Release & Lifecycle

- LAUNCH_SCOPE.md  
- RELEASE_CHECKLIST_v1.md  
- POST_RELEASE_MONITORING.md  

These documents define how GLAi v1 reaches users
and how it is observed afterward.

---

## Audit & Freeze

- AUDIT_v1.md  
- FREEZE_v1.md  

These documents define final authority.
Nothing overrides them within v1.

---

## Authority Rules

- Documents override code
- Earlier layers override later ones
- More restrictive rules override permissive ones
- v1 documents may not be modified without versioning

---

## Version Scope

This index applies to **GLAi v1 only**.

Any change to behavior, architecture, or intent
requires a new version and a new index.

---

## Final Note

If something is unclear,
this index is the first place to look.

If something is missing,
it does not belong to v1.

End of Document
