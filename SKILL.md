---
name: agent-ticket-workflow
description: Run a repo-agnostic agent delivery workflow from Jira idea or ticket to GitHub PR. Use whenever the user asks to do things like start, work on, implement, handle, continue, edit and execute a Jira ticket, Jira issue key, Jira URL, backlog item, story, task, or bug. if planning/execution of a jira ticket is involved, use this skill.
---

# Agent Ticket Workflow

## Operating Model

Drive work through a Jira-to-PR process. Keep this skill repo-agnostic: load and follow repo-local instructions such as `AGENTS.md`, `CLAUDE.md`, `README.md`, task-specific docs, and existing patterns before deciding implementation details.

Keep this top-level skill exposed at startup. Load the referenced step files when that stage is reached, and keep the loaded steps as small as practical.

Go through the workflow stages in order, as needed.

## Workflow

1. **Ticket creation or refinement**: Read `references/01-ticket-creation.md`.
2. **Ticket gate**: Read `references/02-ticket-gate.md`.
3. **Implementation plan creation**: Read `references/03-implementation-plan.md`.
4. **Implementation plan gate**: Read `references/04-implementation-plan-gate.md`.
5. **Implementation**: Read `references/05-implementation.md`.
6. **Review and QA loop**: Read `references/06-review-qa-loop.md`.
7. **GitHub PR**: Read `references/07-github-pr.md`.

## Core Rules
- Start at step 1. Use the gate stages after ticket creation and implementation planning to confirm the previous stage is complete and to get explicit permission before continuing.
- load the next step one by one as the workflow progresses, do not load all steps at once.
- **Do not** skip Stage 1 just because the ticket already exists, it should follow the same process.
- **Do not** skip any stage in the workflow unless the user gave explicit permission.
- Prefer the user's configured connectors for Jira and GitHub when available. If unavailable, use local CLI tools or prepare copy-ready artifacts and tell the user what could not be done.
- Treat the implementation plan as the source of truth during coding; route plan-level changes through plan review unless the user permits a small tactical adjustment.
- After each step remind you and the user of the next step in the workflow and ask if they want to continue.
- In the beginning of each step load the relevant step file into context to make sure you are up to date.