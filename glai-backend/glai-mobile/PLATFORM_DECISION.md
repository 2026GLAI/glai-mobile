PLATFORM_DECISION — Where and How GLAi Exists
Purpose

This document defines where GLAi lives, how it is delivered, and what is deliberately avoided at the current stage.

The goal is sustainability, speed, and cost control — not technological ambition.

Core Principle

GLAi must exist where users already are.

Not where technology is exciting.
Not where prestige is higher.
Where friction is lowest.

Primary Platform Decision
Platform: Mobile Web (PWA-ready)

Chosen

Mobile-first web application

Accessible via browser

QR-code friendly

No installation required

Reasons

97% mobile usage

Zero app store approval risk

Instant updates

No forced user commitment

Lowest maintenance cost

Explicitly Rejected Platforms (for now)
Native Mobile Apps (iOS / Android)

Rejected because

App Store / Play Store dependency

Approval delays

Risk of rejection or removal

Higher development and maintenance cost

Slower iteration

Native apps may be reconsidered only after strong adoption.

Desktop-First Web

Rejected because

Not aligned with real usage

Increases UI complexity

Distracts from mobile clarity

Desktop support is secondary and non-prioritized.

Backend Strategy
Minimal Backend

Chosen

Thin backend layer

Handles:

API proxying

Rate limiting

Security boundaries

Key protection

Avoided

Complex state storage

Heavy user profiling

Long-term session persistence

Backend exists to protect, not to control.

AI Usage Strategy
AI Is a Component, Not the Product

Chosen

External AI models (e.g., Gemini Flash–class)

Strict usage boundaries

Cost-aware interaction design

Rules

AI is called only when necessary

Many interactions are handled without AI

No continuous streaming

No speculative responses

What Is Done Without AI

GLAi deliberately handles the following without AI:

Navigation logic

UI flow

Language detection & switching

Basic informational routing

Error handling language

Stop / pause behavior

This reduces cost and unpredictability.

Cost Control Strategy

AI calls are minimized

First responses are short

Clarification before computation

No background AI processes

No memory-heavy prompts

Every AI call must justify its cost.

Security & Key Protection

Mandatory

No API keys in frontend

All keys stored server-side

Proxy-based access only

Rate limiting enforced

Assumption

Frontend code will be seen

Frontend code may be copied

Security is designed with this reality.

Vendor Dependency Rule

GLAi must be able to:

switch AI providers

degrade gracefully

continue basic operation without AI

No single external provider may block the product.

Deferred Decisions (Intentional)

The following are intentionally postponed:

User accounts

Long-term memory

Personalization

Monetization

Analytics beyond basics

Growth before optimization.

Final Rule

If a platform decision increases:

cost

fragility

dependency

or cognitive load

It is the wrong decision — regardless of how modern it sounds.

End of Document
