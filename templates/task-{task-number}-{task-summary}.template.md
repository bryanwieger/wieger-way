<!--
WORKFLOW PHASE 3 OF 3 — TASK BREAKDOWN
═══════════════════════════════════════════════════════════════════════════════
This document represents a single, atomic unit of work derived from a Finalized
PRD (prd.template.md). Create one file per task, named:

  task-{number}-{short-kebab-case-summary}.md
  Example: task-3-add-apple-pay-button.md

AGENT INTERACTION GUIDE
────────────────────────
Step 1 — Read the Finalized PRD
  Thoroughly read prd.template.md before creating any task files. Do not
  begin task breakdown until that document's status is "Finalized".

Step 2 — Identify atomic units of work
  Decompose the PRD requirements into the smallest independently-deliverable
  pieces. A task is atomic when it can be built, reviewed, and verified
  without depending on incomplete sibling tasks.

Step 3 — Map dependencies
  Identify which tasks must be completed before others can start. Record
  these in the "Depends on" section using the exact filename of the
  blocking task.

Step 4 — Write objective success criteria
  Every success criterion must be a pass/fail statement that a person or
  automated test can verify without ambiguity. Avoid subjective language
  ("clean", "fast", "simple").

Step 5 — Present the task list for approval
  Share the full list of task files with the human before beginning any
  implementation. Confirm scope, order, and success criteria.

Step 6 — Execute & verify
  Work through tasks in dependency order. Update Agent Status as you
  progress. Mark each success criterion as ✅ or ❌ before setting status
  to "Finalized".

RULES
─────
• One task file = one independently testable unit of work.
• Success Criteria must be verifiable by command or checklist — no guessing.
• Do not add scope beyond what the PRD explicitly requires.
• Keep functions ≤ 35 lines and cyclomatic complexity better than the
  majority of the existing codebase unless the PRD states otherwise.
• Do not introduce new dependencies without explicit human approval.
═══════════════════════════════════════════════════════════════════════════════
-->

# Agent Instructions
- Write outputs in this document under the correct sections.
- Keep the task independently executable and verifiable.
- Use objective success checks, test cases, and edge coverage.

# Agent Status
<!--
Valid values:
  To Do         — Work has not started on this task.
  In Progress   — The agent is actively implementing this task.
  In Review     — Implementation is complete; awaiting human or CI verification.
  Finalized     — All success criteria have been verified as passing.
-->
To Do

# Depends on
<!--
List every task file that must reach "Finalized" status before this task
can begin. Use exact filenames so the dependency graph is unambiguous.

Example:
  - task-1-create-stub-api-endpoint.md
  - task-2-add-database-schema.md

If this task has no dependencies, write "None".
-->
- 

# Task Overview
<!--
One sentence that states the goal of this task clearly enough that an
engineer who has not read the PRD can understand what must be built.

Example:
  "Add an Apple Pay button to the mobile checkout form that initiates a
   payment session via the existing PaymentService."
-->
- 

# Inputs
<!--
List every file, API, service, environment variable, or data source the
agent is allowed to read from or write to while completing this task.
Being explicit here prevents unintended side effects.

Example:
  - src/components/CheckoutForm.tsx (modify)
  - src/services/PaymentService.ts (read only — do not modify)
  - APPLE_PAY_MERCHANT_ID environment variable (read)
  - Stripe API — /v1/payment_intents endpoint
-->
- 

## Hints
<!--
Optional starting points, architectural patterns, or relevant prior art
that may help the agent begin. These are suggestions, not requirements.

Example:
  - See the existing GooglePayButton component in src/components/GooglePayButton.tsx
    for the pattern to follow.
  - The PaymentService.initSession() method accepts a `provider` parameter.
-->

# Constraints
<!--
Hard limits that apply specifically to this task. These should be derived
from the PRD Constraints section plus any task-specific engineering limits.

Example:
  - Must not modify PaymentService.ts (owned by the Payments team; separate PR).
  - No new npm dependencies without approval.
  - Button must render in under 100 ms on a mid-range Android device.
-->
- 

# Expected Output
<!--
Concrete list of deliverables when this task is complete. Be specific about
file paths, artifact names, or observable system behaviors.

Example:
  - New file: src/components/ApplePayButton.tsx
  - Modified file: src/components/CheckoutForm.tsx (ApplePayButton rendered on mobile)
  - New test file: src/components/ApplePayButton.test.tsx
  - Brief test report confirming all tests pass (paste output or link to CI run)
-->
- 

# Success Criteria
<!--
Objective, numbered pass/fail checklist. Every item must be verifiable by
running a command, reading an output, or checking a UI state. The agent
must confirm each item before setting Agent Status to "Finalized".

Example:
  1. A test file exists that covers the ApplePayButton component.
  2. All tests pass: `npm test -- --testPathPattern=ApplePayButton`.
  3. The button is visible on viewports < 1024 px and hidden on wider viewports.
  4. The button is not rendered when Apple Pay is unavailable in the browser.
  5. No new functions exceed 35 lines of code.
  6. No new external dependencies were added to package.json.
-->
1. 

# Test Cases
<!--
Concrete input/output pairs that define correct behavior. Each test case
should map to one or more success criteria.

Format:
  <ID>. Given <precondition>, when <action>, then <expected result>.

Example:
  1. Given a mobile viewport (width = 375 px) and Apple Pay is available,
     when the checkout form renders, then the Apple Pay button is visible.
  2. Given Apple Pay is NOT available in the browser,
     when the checkout form renders, then the Apple Pay button is not in the DOM.
  3. Given a desktop viewport (width = 1440 px),
     when the checkout form renders, then the Apple Pay button is not visible.
-->
1. 

# Edge Cases
<!--
Non-happy-path scenarios and the behavior the system must exhibit for each.
Edge cases should cover failure modes, boundary values, and unexpected inputs.

Example:
  1. Apple Pay session times out mid-flow → show a user-facing error toast;
     do not leave the checkout form in a broken state.
  2. PaymentService.initSession() throws a network error → surface an error
     message; the user can retry without refreshing the page.
  3. User taps Apple Pay button twice in rapid succession → only one payment
     session is initiated (debounce or disable button after first tap).
-->
1. 

# Evaluation Method
<!--
Step-by-step instructions for verifying that this task is complete.
Include exact commands, URLs, or manual steps a reviewer can follow.

Example:
  1. Run `npm test -- --testPathPattern=ApplePayButton` — all tests must pass.
  2. Run `npm run lint` — zero new lint errors.
  3. Open http://localhost:3000/checkout on a 375-px-wide viewport in Chrome.
     Confirm the Apple Pay button is visible.
  4. Open the same URL at 1440 px width. Confirm the button is not visible.
  5. Simulate Apple Pay unavailability via DevTools (disable the API) and
     confirm the button is absent from the DOM.
-->
-

