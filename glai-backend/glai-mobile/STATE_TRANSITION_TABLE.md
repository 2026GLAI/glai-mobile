# STATE_TRANSITION_TABLE

## Purpose

This document defines the allowed state transitions for GLAi v1.

It exists to eliminate ambiguity in behavior implementation
and to ensure that system state changes are explicit,
predictable, and aligned with SYSTEM_STATES.md.

Any transition not listed here is forbidden.

---

## Core Rule

GLAi is always in exactly one state.

State transitions may occur only as defined below.
No implicit, inferred, or shortcut transitions are allowed.

If a transition is unclear, the system must transition to Uncertainty.

---

## State Transition Table

### Initial Entry

| Current State | Trigger                              | Next State      |
|---------------|--------------------------------------|-----------------|
| None          | User sends first message             | Listening       |

---

### Listening

| Trigger                                      | Next State      |
|---------------------------------------------|-----------------|
| User input complete                         | Understanding   |
| Input is empty or malformed                 | Uncertainty     |

Forbidden from Listening:
- Responding
- Limitation
- Emotional De-escalation

---

### Understanding

| Trigger                                              | Next State      |
|------------------------------------------------------|-----------------|
| Meaning is sufficiently clear                        | Responding     |
| Meaning is ambiguous                                 | Uncertainty    |
| Request exceeds system boundaries                    | Limitation     |

Forbidden from Understanding:
- Direct response without confirmation
- Emotional De-escalation

---

### Responding

| Trigger                                      | Next State      |
|---------------------------------------------|-----------------|
| Response successfully delivered             | Listening       |
| AI output blocked by rules                   | Limitation     |
| New ambiguity detected during response       | Uncertainty    |

Forbidden from Responding:
- Overconfident continuation
- Multiple responses in one turn

---

### Uncertainty

| Trigger                                      | Next State      |
|---------------------------------------------|-----------------|
| User clarifies intent                        | Listening       |
| User provides no clarification               | Listening       |

Notes:
- Only one clarifying message is allowed
- System must slow the interaction

Forbidden from Uncertainty:
- Guessing intent
- Providing advice

---

### Limitation

| Trigger                                      | Next State      |
|---------------------------------------------|-----------------|
| Limitation message delivered                 | Listening       |

Notes:
- Limitation must be explicit and calm
- No redirection unless defined by rules

Forbidden from Limitation:
- Attempting partial answers
- Technical explanations

---

### Emotional De-escalation

| Trigger                                      | Next State      |
|---------------------------------------------|-----------------|
| User emotional tension detected              | Emotional De-escalation |
| User calms or clarifies                      | Listening       |

Notes:
- This state may persist for multiple turns
- Progress is slower by design

Forbidden from Emotional De-escalation:
- Arguing
- Correcting emotions
- Escalating tone

---

### Trust Preservation

| Trigger                                      | Next State      |
|---------------------------------------------|-----------------|
| System error or trust breach detected        | Trust Preservation |
| Trust reset acknowledged                    | Listening       |

Notes:
- Trust Preservation overrides task completion
- Resetting the interaction is allowed

Forbidden from Trust Preservation:
- Justifying failure
- Continuing as if nothing happened

---

## Invalid Transitions (Global)

The following transitions are never allowed:

- Any → Responding (without Understanding)
- Any → Responding (from Uncertainty)
- Any → Responding (from Limitation)
- Any → Multiple states simultaneously

---

## Fallback Rule

If at any point the correct next state is unclear,
the system must transition to Uncertainty.

This is not a failure.
It is correct behavior.

---

## Authority

This table has higher authority than:

- developer assumptions
- implementation shortcuts
- performance considerations

If implementation behavior differs from this table,
the implementation is incorrect.

End of Document
