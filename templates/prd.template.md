<!--
WORKFLOW PHASE 2 OF 3 — REQUIREMENTS DEFINITION
═══════════════════════════════════════════════════════════════════════════════
This document is written AFTER questions.template.md reaches "Finalized" status.
The agent synthesizes everything gathered in Discovery into a structured,
decision-ready PRD that can be handed to engineers without further clarification.

AGENT INTERACTION GUIDE
────────────────────────
Step 1 — Read Discovery output
  Thoroughly read the completed questions.template.md. Do not begin this
  document until that file's status is "Finalized".

Step 2 — Draft all sections
  Fill in every section below using the information from Discovery. Where
  information is missing, note it in "Open Questions to the human" rather
  than guessing.

Step 3 — Present for review
  Share the drafted PRD with the human. Ask them to confirm that the Problem
  Statement, User Stories, and Requirements correctly capture their intent.

Step 4 — Iterate
  For every piece of feedback or new question, update the relevant section and
  move clarifying questions to "Open Questions to the human". Clear that
  section once each question is answered and the doc is updated.

Step 5 — Finalize & hand off
  When the human approves all sections, set Agent Status to "Finalized".
  Use this document as the sole input when creating task files
  (task-{n}-{summary}.template.md). Create one task file per atomic unit of work.

RULES
─────
• Write every requirement as an observable behavior, not an implementation guess.
  ✓ "The system returns a 401 response when an unauthenticated user calls /api/orders."
  ✗ "Use JWT middleware to protect the orders endpoint."
• Success Criteria must be measurable — avoid "fast", "easy", or "better".
• Constraints must be hard limits, not preferences.
• Never add scope without explicit human approval.
═══════════════════════════════════════════════════════════════════════════════
-->

# Agent Instructions
- Write all outputs directly in this document under the relevant sections.
- Keep this PRD decision-ready: concrete, testable, and scoped.
- Resolve ambiguity by asking clarifying questions before finalizing requirements.
- Write requirements as observable behaviors, not implementation guesses.
- Ensure success criteria and constraints are measurable and non-conflicting.

# Agent Status
<!--
Valid values:
  To Do         — The agent has not yet begun drafting this PRD.
  In Review     — A draft has been shared with the human; awaiting feedback.
  Finalized     — The human has approved all sections; ready to create task files.
-->
To Do

# Problem Statement
<!--
One concise paragraph that answers: What is broken or missing, who is affected,
and what is the cost of inaction?
Example:
  "Checkout users on mobile devices abandon the cart at a 62 % rate because the
   payment form requires 14 fields on a single screen. This costs an estimated
   $120 k/month in lost revenue. No mobile-optimized flow currently exists."
-->
- 

# Scope
## In Scope
<!--
List the specific capabilities or behaviors that WILL be built or changed.
Be precise — vague scope leads to scope creep.
Example:
  - Condensed mobile payment form (≤ 5 visible fields at a time)
  - Auto-fill support for Apple Pay and Google Pay
  - A/B test framework hooks so Marketing can run experiments
-->
- 

## Out of Scope
<!--
Explicitly list what will NOT be addressed in this iteration, even if related.
This prevents misaligned expectations and protects the team's focus.
Example:
  - Desktop checkout redesign (separate initiative)
  - Saved payment methods (deferred to Q3)
  - Refund flow changes
-->
- 

# User Stories
<!--
Each story follows the format: "As a <role>, I want <capability>, so that <outcome>."
Write at least one story per distinct user type. Stories must be testable —
avoid stories where "I want" is vague or the "so that" is immeasurable.
-->

## End user
<!--
The person who directly uses the product or feature day-to-day.
Example:
  - As a mobile shopper, I want to complete checkout in under 60 seconds,
    so that I don't abandon my cart out of frustration.
-->
- As a ..., I want ..., so that ...

## Paying admin
<!--
The person who manages accounts, billing, or configuration on behalf of others.
Example:
  - As a store admin, I want to see a daily summary of abandoned carts with
    their last step reached, so that I can identify drop-off patterns.
-->
- As a ..., I want ..., so that ...

## On-call engineering (system logs & metrics)
<!--
Engineers who need observability into the system's health and behavior.
Example:
  - As an on-call engineer, I want structured logs emitted for each checkout
    step, so that I can pinpoint failures without reading source code.
-->
- As a ..., I want ..., so that ...

## Business analyst (user metrics)
<!--
People who analyze usage data to inform product decisions.
Example:
  - As a business analyst, I want funnel-step events sent to our analytics
    platform, so that I can calculate conversion rates per step.
-->
- As a ..., I want ..., so that ...

## Security
<!--
Security engineers or compliance requirements that must be satisfied.
Example:
  - As the security team, I want all payment data transmitted over TLS 1.2+
    and never logged in plain text, so that we remain PCI-DSS compliant.
-->
- As a ..., I want ..., so that ...

# Requirements
<!--
Numbered list of specific, testable behaviors the system MUST exhibit.
Each requirement should map to one or more user stories and one or more
success criteria. Write them as facts about the system, not tasks for the team.

Format: <ID>. <System> <verb> <observable condition> [when <trigger>].

Example:
  1. The checkout form displays no more than 5 input fields at a time on
     viewports narrower than 768 px.
  2. The system emits a `checkout.step_completed` event to the analytics
     pipeline within 500 ms of each step submission.
  3. Payment data is never written to application logs in any environment.
-->
1. 

# Success Criteria
<!--
Objective, pass/fail statements that define when this PRD is "done".
Each criterion must be verifiable by a human or automated test.

Example:
  1. Mobile checkout conversion rate increases by ≥ 10 % within 14 days
     of launch (measured via Analytics dashboard).
  2. All existing desktop checkout end-to-end tests continue to pass.
  3. Zero PCI-related findings in the next quarterly security scan.
-->
1. 

# Constraints
<!--
Hard limits that cannot be negotiated. Include technical, legal, budgetary,
or timeline constraints. Distinguish these from preferences or guidelines.

Example:
  - Must not introduce new third-party payment processors (legal review required).
  - Must be backward-compatible with iOS 14 and Android 10.
  - No new cloud infrastructure — solution must run within existing AWS account.
-->
- 

# Assumptions
<!--
Facts the team is treating as true but has not verified. If any assumption
turns out to be false, the PRD may need to be revisited.

Example:
  - Apple Pay and Google Pay are already enabled on the merchant account.
  - The analytics pipeline accepts events in the existing JSON schema.
  - The A/B test framework is already deployed and does not require new infra.
-->
- 

# Notes
<!--
Supplementary context, design considerations, or decisions that don't fit
elsewhere but should be preserved for future reference.

Example:
  - The design team has a Figma prototype at [link] that informed the field
    count constraint.
  - Engineering estimated 2 weeks for the form refactor, 1 week for analytics.
-->
-

# Open Questions to the human
<!--
Use this section to surface any remaining ambiguity that blocks completing a
section above. As the human answers, update the relevant section, then remove
the resolved question from here.

Lifecycle of a question:
  1. Agent adds question here.
  2. Human answers (inline or in conversation).
  3. Agent updates the relevant PRD section with the answer.
  4. Agent removes the question from this section.

Example:
  Q: Should the condensed form also apply to tablet viewports (768–1024 px)?
  → Human: Yes, apply it to anything under 1024 px.
  → Agent: Updates the Requirements section, removes this question.
-->
