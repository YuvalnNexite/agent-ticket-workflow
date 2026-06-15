# Implementation Plan Creation

Use this stage to translate a confirmed, concrete Jira ticket into a simple, concise, exact, goal-oriented implementation plan detailed enough for a coding agent and easy for a human to verify.

## Required Context

- Jira key, title, issue type and parent issue if any.
- Acceptance criteria.
- Relevant context from the ticket description, comments, linked issues, dependencies, constraints and validation expectations.
- Repo-local instructions such as `AGENTS.md`, `CLAUDE.md`, `README.md`, contribution docs, architecture docs and test instructions.
- Relevant code paths, owners, existing patterns and dependency constraints.

If required ticket context is missing or vague, return to `references/01-ticket-creation.md`.

## Planning Workflow

During this stage, inspect the code enough to understand how the change should actually be implemented, then plan the full change before asking the human to review anything. The agent should think through the likely code edits, affected files, tests, QA, rollout concerns and edge cases up front, while keeping track of assumptions and questions alongside recommendations or suggested answers grounded in best practices, good taste, and reasonable scope control.

Suggested flow:

1. Inspect the likely code paths and form a concrete implementation approach.
2. Plan the change, affected files, tests, QA and validation approach.
3. Look for the impact and downstream impact the change causes, edit the plan accordingly. 
4. Keep track of assumptions and questions that affect scope, behavior, implementation choices, data shape, testing, rollout or risk.
5. For each assumption or question, include recommendations with good engineering judgment. Include Both the best and most practical/efficient way. mark questions and assumptions with numbers and recommendations with letters for easy reference.
6. Show the implementation plan first, as you currently believes the change should be done.
7. After the plan, show the assumptions and questions with their recommendations, then ask the human to review and answer them.
8. Update the plan, assumptions and questions based on the answers.
9. Add any new assumptions or questions created by those answers.
10. Repeat until the human explicitly says the plan is good.

Suggested working format:

```markdown
## Implementation Plan

## Assumptions And Questions

```

## Plan Template

```markdown
# Implementation Plan

Ticket:
Title:
Branch:

## Goal/Summary
- One or two sentences describing the implementation outcome, not the product background.

## Scope

## Key Changes
- The actual planned changes with sub-tasks. this is the main point where when you read it you understand what the actual change is

## Data / DB / Migration Work
- like Migrations, Backfills, Rollback considerations and schema changes (referance if a small script is needed for consistent changes).

## Business Logic And Context
- if applicable

## Tests And QA
- All types of tests, QA and DQA that makes sence given the plan. the idea is to make sure the change is correct and works.
```

## Planning Rules

- Keep the plan simple and concise.
- Take ticket context into account when creating the plan.
- Plan all the way through before asking for review; and reason about the likely implementation.
- Keep wording concise and exact.
- Include change location.
- Include tests, code reviews, QA and DQA when needed.
- Include DB migrations when they are needed.
- Follow repo-local instructions.
- Prefer simple, reversible changes over broad refactors.
- Iterate on the plan and the assumptions/questions together until the user gives explicit permission that the plan is good.
- Prefer existing dependencies over creating new ones.
- edit the sections according to what makes the most sense, the template is a recommendation, the main goal is to have the best plan for the implementation step.

## Output

Present the implementation plan in full first, then the assumptions and questions with recommendations and ask the human to review and answer them. Iterate until the user explicitly says the plan is good. Hold off on implementation until that approval is clear.


## Jira handling

- Leave the status short of `Done`; the user will decide when it is ready to move there.
- include the tickets (with a working link) in the final summary alongside the plan.
- keep the Jira ticket updated with the working plan

