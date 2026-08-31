# AI Agent Workflow

This repo uses existing tools only: GitHub or Linear for backlog, Codex for implementation, and a separate Codex review pass for quality control.

## Start Here

1. Create a small backlog item using the `AI task` issue template.
2. Make sure the issue has clear acceptance criteria.
3. Ask an implementation agent to work on exactly that issue.
4. Open a pull request with the PR template.
5. Ask a separate review agent to review the PR or diff.
6. Fix blocking review findings.
7. Merge only after CI and human approval.

## Suggested Labels

- `ai-ready`: clear enough for an agent to start.
- `ai-working`: currently assigned to an implementation agent.
- `ai-review`: waiting for independent AI review.
- `ai-needs-human`: blocked on product, design, credentials, or permissions.
- `ai-done`: implemented, reviewed, and accepted.

## Example Implementation Prompt

```text
Take GitHub issue #123. Read the issue and AGENTS.md first.
Create a scoped implementation plan, make the minimal code change, run the requested checks,
and prepare a pull request summary. Do not merge.
```

## Example Review Prompt

```text
Review PR #456 against the base branch. Follow AGENTS.md, especially Code Review Rules.
Prioritize bugs, regressions, security, data loss, API contract issues, and missing tests.
Do not modify files. Return findings first with file and line references.
```

## Linear Variant

If the backlog lives in Linear, keep the same states:

- Ready for AI
- In AI implementation
- In AI review
- Needs human
- Done

Assign only well-scoped issues to Codex. If an issue is large, split it before delegation.
