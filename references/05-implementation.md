# Implementation

Use this stage to execute the approved plan in the target repository.

## Process

1. Collect the context you need such as: 
   1. The ticket.
   2. the Plan
   3. repo-local instructions.
   4. current git status.
   5. relevant files
2. Create or switch to an appropriate branch when requested or when the workflow expects a PR.
3. Make the changes required by the approved plan.
4. Follow existing patterns, naming, architecture, and test style.
5. Update or create tests alongside behavior changes.
6. Keep notes on deviations, discoveries, and commands to run in QA.

## Implementation Rules

- Prefer existing dependencies over creating new ones.


## Handoff To QA

Before entering QA, prepare a short checklist:

- Changed files.
- Tests added or updated.
- Commands expected to validate the change.
- Known risks or manual checks.
