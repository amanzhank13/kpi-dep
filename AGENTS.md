# AGENTS.md

## Purpose

This repository is set up for a simple AI-agent workflow:

1. A backlog item describes the work.
2. One implementation agent makes a small, isolated change.
3. A separate review agent reviews the diff or pull request.
4. A human decides whether to merge.

## Working Rules

- Work on one backlog item at a time.
- Prefer a dedicated branch named `codex/<issue-id>-short-description` when branch creation is part of the task.
- Read the issue, acceptance criteria, and relevant files before editing.
- Keep changes scoped to the requested behavior.
- Do not make unrelated refactors, formatting sweeps, dependency upgrades, or metadata churn.
- Do not commit secrets, credentials, local config, generated caches, or personal data.
- Do not merge pull requests or push destructive git changes unless the user explicitly asks.
- If the task is ambiguous or acceptance criteria are missing, ask for clarification before implementing.

## Implementation Checklist

Before handing work back, an implementation agent should report:

- What changed.
- Which files changed.
- Which tests, linters, builds, or manual checks were run.
- Any known gaps, skipped checks, or follow-up risks.

## Pull Request Expectations

Every pull request should include:

- A link to the issue or backlog item.
- A short summary of the behavior change.
- Verification evidence with exact commands where possible.
- Screenshots or recordings for visible UI changes.
- Notes for anything intentionally left out.

## Code Review Rules

Review agents should act independently from the implementation agent.

- Review the diff against the intended base branch.
- Prioritize correctness, regressions, data loss, security, migrations, permissions, API contracts, and missing tests.
- Findings must lead the review, ordered by severity.
- Include file and line references for actionable issues.
- Avoid style-only comments unless they block maintainability or violate local conventions.
- Do not modify the working tree during review.
- If there are no blocking findings, say that clearly and mention any residual test gaps.

## Done Definition

A task is done only when:

- The acceptance criteria are satisfied.
- Relevant checks pass or skipped checks are explained.
- The review agent has no blocking findings.
- A human has approved the final result for merge.
