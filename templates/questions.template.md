<!--
WORKFLOW PHASE 1 OF 3 — DISCOVERY
═══════════════════════════════════════════════════════════════════════════════
This is the starting point of the Wieger Way. Before any solution is designed
or code is written, the agent must fully understand the problem space.

AGENT INTERACTION GUIDE
────────────────────────
Step 1 — Greet & orient
  Introduce yourself and ask the human to describe the problem they want to
  solve in their own words. Do not suggest solutions yet.

Step 2 — Ask grouped questions
  Organize follow-up questions by theme (see the Questions section for
  guidance). Ask one theme-group at a time so the human is not overwhelmed.

Step 3 — Listen & update
  After each response, update Resources, User Context, and the Questions
  section to reflect what you have learned. Strike through answered questions
  and add new ones that surface from the answers.

Step 4 — Know when to stop
  Stop asking when no major ambiguity remains about the users, the problem,
  the constraints, or the definition of success. Set Agent Status to
  "Finalized" and inform the human you are ready to draft the PRD.

Step 5 — Hand off
  Use this completed document as the primary input when filling in
  prd.template.md. Do not discard any context gathered here.

RULES
─────
• Never ask more than 3 questions at once.
• Never propose solutions during discovery — focus only on understanding.
• Always update this document before asking the next round of questions.
• Link every resource to its source; do not paraphrase without attribution.
═══════════════════════════════════════════════════════════════════════════════
-->

# Agent Instructions
- Set `Agent Status` to reflect progress: `To Do`, `Waiting for Human`, or `Finalized`.
- Ask focused discovery questions that remove ambiguity and uncover constraints.
- Keep questions concise, grouped by theme, and ordered by impact.
- Capture only relevant evidence in Resources; link sources when available.
- When status is `Finalized`, use this document as the sole input to produce the PRD.

# Agent Status
<!--
Valid values:
  To Do         — The agent has not yet begun asking questions.
  Waiting for Human — Questions have been sent; awaiting the human's response.
  Finalized     — All critical ambiguities are resolved; ready to write the PRD.
-->
To Do

# Resources
<!--
Capture every reference the human or agent mentions. Link to sources rather
than paraphrasing so the PRD author can verify context directly.
-->

## Code Repos
<!--
List repositories or local directories that are relevant to the problem.
Example: https://github.com/acme/payments-service (owns the checkout flow)
Example: /home/dev/projects/payments-service (local clone)
-->
- 

## Logs
<!--
Paste or link to error logs, stack traces, or system output that illustrates
the problem. Include timestamps and environment (prod / staging / local).
Example: https://datadog.com/logs?query=service:api  (showing 503s since 2024-01-10)
-->
- 

## Metrics
<!--
Link to dashboards or share data that quantifies the problem.
Example: P95 latency = 4.2 s (target < 1 s) — Grafana dashboard link
-->
- 

## Documentation
<!--
Link to existing specs, wikis, runbooks, or API docs the agent should read.
Example: https://wiki.acme.com/api-spec — current checkout API contract
-->
- 

## Research
<!--
Competitive analysis, prior user interviews, articles, or market data.
Example: Competitor X solves this with feature Y — https://example.com/blog/y
-->
- 

# User Context
<!--
Describe who the human is and what role they play. This helps the agent
tailor questions and recommendations to the right level of detail.
Example:
  "Maria is a product manager at a B2B SaaS company. She owns the onboarding
   flow. Her team ships every two weeks and uses React + Node.js."
-->
- 

# Questions
<!--
Group questions by theme. Ask the highest-impact group first. After the human
answers, mark those questions resolved and add new ones if needed.

SUGGESTED THEMES (use, rename, or skip as appropriate):

  Users & stakeholders
    1. Who are the primary users of this feature? (role, technical level)
    2. Are there secondary users, admins, or external systems that interact with it?

  Problem & goals
    3. What does success look like immediately after deploying to production?
    4. How is the problem currently handled without this feature?
    5. What is the cost of NOT solving this? (lost revenue, user churn, manual effort)

  Technical context
    6. Are there existing systems or APIs this must integrate with?
    7. Are there known performance, security, or compliance constraints?
    8. What languages, frameworks, or infrastructure are already in use?

  Prioritization & scope
    9.  Are there other features or work items that must ship first?
    10. What is out of scope for this iteration?
-->
1. 
