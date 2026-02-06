# TECH_STACK_LOCK

## Purpose

This document locks the technology stack for GLAi v1.

Its role is to prevent technology-driven drift,
scope creep disguised as optimization,
and post-freeze re-interpretation of technical choices.

After this lock, technology serves behavior — not ambition.

---

## Lock Authority

This document derives authority from:

- TECH_STACK.md
- ARCHITECTURE_MINIMAL.md
- FREEZE_v1.md
- IMPLEMENTATION_GUARD.md

If a conflict exists, the most restrictive rule applies.

---

## Locked Stack (v1)

The following stack elements are locked for v1:

- Mobile-first web client (PWA or equivalent)
- Minimal frontend (HTML, CSS, minimal JS/TS)
- Single backend gateway
- One external AI provider (as defined)
- Server-side state authority
- Explicit session-based interaction

No substitutions are allowed unless explicitly permitted below.

---

## What “Locked” Means

Locked means:

- no framework replacement
- no architectural refactoring
- no language migration
- no infrastructure expansion
- no abstraction layers “for the future”

The stack is considered sufficient as-is.

---

## Allowed Exceptions

Changes are allowed **only** if:

- a critical security vulnerability is discovered
- a legal or compliance requirement forces change
- a blocking production bug has no other remedy

In all cases:
- behavior must remain identical
- trust rules must remain intact
- scope must not expand

Each exception must be documented.

---

## Forbidden Motivations

The following motivations are explicitly invalid:

- performance benchmarking
- developer preference
- community trends
- investor suggestion
- perceived scalability needs
- “best practices” not tied to v1 documents

v1 is not a résumé project.

---

## Dependency Lock

All dependencies used in v1 must be:

- minimal
- explicit
- version-pinned

Adding a dependency requires justification
against IMPLEMENTATION_GUARD.md.

If a dependency can be removed safely,
it should be removed.

---

## Infrastructure Lock

Infrastructure decisions must remain:

- simple
- observable
- reversible

Auto-scaling, multi-region setups,
and complex CI/CD pipelines are postponed.

Stability beats sophistication.

---

## AI Provider Lock

The chosen AI provider is locked for v1.

- No provider switching
- No multi-provider logic
- No fallback orchestration

If the provider fails,
the system must degrade gracefully —
not adapt silently.

---

## Version Boundary Rule

Any desire to change the stack
indicates the need for a new version.

Stack changes do not belong to v1.x.

They belong to v2.

---

## Final Lock Rule

If a technical discussion begins with:
“Technically, it would be better if…”

The discussion is over.

GLAi v1 is intentionally constrained.

End of Document
