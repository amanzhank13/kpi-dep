# kpi-dep

This repository is a small test project for an AI-agent development workflow.
It is intended to show how a backlog item can move from a clear task description
through implementation, review, and eventual human approval.

## Workflow

Work is tracked through GitHub Issues. Each issue should describe one scoped task
with clear acceptance criteria.

For each task:

1. An implementation agent reads the issue and repository instructions.
2. The implementation agent makes a focused change for that issue only.
3. A pull request is opened with a summary and verification notes.
4. A separate AI review pass checks the diff for bugs, regressions, missing tests,
   and other risks.
5. A human reviews the result and decides whether to merge.

Pull requests should receive AI review before they are merged by a human.

## AI Workflow Checklist

- [ ] Create a GitHub issue with a scoped task and acceptance criteria.
- [ ] Have an implementation agent make the focused change.
- [ ] Open a PR with a summary and verification notes.
- [ ] Run a separate AI review of the diff.
- [ ] Have a human review and merge after approval.

See [docs/ai-agent-workflow.md](docs/ai-agent-workflow.md) for the fuller process.
