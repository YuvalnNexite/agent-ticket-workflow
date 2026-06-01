# Review And QA Loop

Use this stage after implementation to review, test, lint, QA, fix issues, and repeat until the result is ready for PR or blocked.

## Review Pass

Review the diff as if reviewing someone else's PR:

- Behavioral regressions.
- Missing or weak tests.
- Error handling, edge cases, concurrency, data correctness, security, and migration safety.
- Scope creep or unnecessary complexity.
- Repo-local style and architecture mismatches.
- Compare the changes to the plan and ticket to see its all addressed

## Validation Pass

Run the checks appropriate for the repo and plan:

- Unit tests for changed logic.
- Integration or workflow tests for cross-module behavior.
- Lint, formatting, type checks, static analysis, or SQL validators when present.
- Manual QA or local app verification when automated coverage is insufficient.
- Migration validation or dry-runs where relevant.

## Loop

1. Run review and validation.
2. Analyze the results.
3. If issues are found, return to implementation, fix them, and rerun the relevant checks.
4. Repeat until checks pass or a real blocker remains.

## Reporting

Track:

- Commands run.
- Pass/fail result.
- Fixes made after failures.
- Checks not run and why.
- Residual risks.
