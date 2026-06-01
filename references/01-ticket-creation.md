# Ticket Creation

Use this stage to turn a user idea, bug, parent ticket, or under-specified existing Jira ticket into a clear Jira story, task, or subtask with clean boundaries and enough context for the next stages.

## Process

1. Gather context from the user, existing Jira issues, and the product or business context around the request.
2. If an existing Jira issue was supplied, assess whether it already matches the draft template and quality bar below.
3. Treat the ticket as under-specified when it lacks concrete acceptance criteria, understandable scope, key assumptions, or contains vague language such as "and more", "etc.", "fix weirdness", or similar open-ended wording.
4. Decide the issue type: story for user-facing capability, task for technical work, subtask when the user gives a parent issue.
5. Draft a new or refined ticket and show it in full to the user before creating or updating it.
6. Iterate and ask questions and reiterate assumptions until you are both on the same page and the user explicitly approves the ticket.
7. Create or update the Jira issue after confirmation.
8. Report the key, link, and final title.

## Draft Template

```markdown
Title:

Issue type:
Parent:

Problem / Opportunity:

Desired outcome:

Out of scope:

Acceptance criteria:

Missing Information:

Additional context:
```

## Quality Bar

- Acceptance criteria should be concrete, testable, and more specific than a restatement of the task.
- Scope delimitation should make it easy for an implementation agent to avoid overbuilding.
- Missing Information should call out missing product, data, design, permission, environment, migration, or API decisions.
- Additional context should capture the intent, constraints, and non-goals clearly enough that later stages can plan the work without guessing the product logic.
- Existing Jira tickets that fall short of this quality bar are usually worth refining before implementation planning. The presence of a Jira key, assignee, sprint, or status is not much evidence on its own that the ticket is ready.
