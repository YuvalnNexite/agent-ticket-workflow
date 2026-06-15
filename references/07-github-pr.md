# GitHub PR

Use this stage to publish the completed and QA'd implementation. Default to GitHub because this workflow targets GitHub PRs, but follow repo-local instructions if the repository uses a different host or PR process.

## Process

1. Inspect git status and confirm the intended files are included.
2. Create a focused commit or commits if the user wants commits created.
3. Push the branch.
4. Create a PR against the repo's expected branch.
5. Include ticket link/key, summary, tests, QA, risks, screenshots or artifacts when relevant, and follow-up items.
6. Check on CI/CD untill it passes. If it fails fix the issues.

## PR Template

```markdown
## Summary
- 

## Ticket
- 

## Implementation
- 

## Tests / QA
- 

## Risks / Rollout
- 
```

## Rules

- Use the repo's PR template if one exists.
- Follow the repo's instruction on the matter.
- If GitHub tools are unavailable, provide the exact PR title/body and state that PR creation was not performed.
