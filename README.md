# agent-ticket-workflow

A reusable agent skill for driving ticket-based work from ticket refinement through planning, implementation, QA, and PR creation.

## Underlying Principles

- Repo-agnostic: define a reusable delivery process and defer repository-specific rules, patterns, and tooling to repo-local instructions.
- Modular: keep the skill split into small stage files with clear responsibilities.
- Minimal: keep the top-level surface small and stable, and move stage detail into references.
- Progressive: load instructions incrementally instead of front-loading the entire workflow into context.
- Model-leveraging, not micromanaging: provide structure, gates, and quality bars without hard-coding every execution detail.
- Durable to model improvement: prefer principles and decision boundaries over brittle instructions that assume one fixed working style.
- As simple as possible: keep only rules that materially improve reliability, clarity, or quality.
- Graceful under limited tooling: keep the workflow usable even when Jira or GitHub integrations are unavailable by falling back to copy-ready artifacts.

## What It Expects

- A host that supports `SKILL.md`-style skills and relative `references/` loading.
- A repository or workspace with local instructions when available, such as `AGENTS.md`, `CLAUDE.md`, or `README.md`.
- A human in the loop for explicit confirmation at the ticket gate and implementation-plan gate.

## Recommended Integrations

This skill works best when the agent has access to both Jira and GitHub through either:

- native connectors or integrations, or
- local CLI tools and credentials

Recommended capabilities:

- Jira: read tickets, create/update tickets, add comments, and create subtasks or linked tasks.
- GitHub: inspect branches and PRs, push branches, and create pull requests.

If those integrations are unavailable, the skill should still be usable by preparing copy-ready ticket text, implementation plans, and PR text for a human to apply manually.

## Install

Copy this folder into the skill location used by your agent setup.

Common locations:

- Codex: `~/.codex/skills/agent-ticket-workflow/`
- Claude Code: `~/.claude/skills/agent-ticket-workflow/`

The folder should contain:

- `SKILL.md`
- `references/`
- `agents/` if your host uses it

## Workflow Summary

1. Ticket creation or refinement
2. Ticket gate
3. Implementation plan creation
4. Implementation plan gate
5. Implementation
6. Review and QA loop
7. GitHub PR

## Recommendations

- Keep repo-specific rules in repo-local files rather than baking them into this skill.
- Prefer connectors or CLI access for Jira and GitHub before relying on manual copy-paste workflows.
- Use the skill as a process wrapper, not as a substitute for repository-specific engineering judgment.
