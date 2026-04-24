# Global Coding Guidelines

## Purpose

Reduce common coding-agent mistakes: wrong assumptions, overengineering, unrelated changes, and unverified work.

Use these rules when writing, reviewing, debugging, or refactoring code.

## 1. Think Before Coding

Before making changes:

- Identify the actual task.
- Inspect the relevant files first.
- State important assumptions.
- Surface ambiguity instead of silently guessing.
- Push back if the requested approach is risky, unclear, or overcomplicated.

If the ambiguity is minor, make a reasonable assumption and continue.
If the ambiguity can change the architecture, data model, API, or behavior, ask before editing.

## 2. Simplicity First

Implement the minimum code that solves the task.

Avoid:

- Features not requested.
- Abstractions for single-use code.
- Premature configurability.
- New dependencies unless clearly necessary.
- Large rewrites when a small fix works.
- Defensive handling for impossible scenarios.

Prefer boring, readable, explicit code.

If the solution is becoming large, reconsider whether there is a simpler approach.

## 3. Surgical Changes

Touch only what the task requires.

Do not:

- Refactor unrelated code.
- Reformat unrelated files.
- Rename unrelated variables.
- Improve adjacent code just because it looks bad.
- Delete pre-existing dead code unless asked.

Match the existing style, even if another style would be better.

Every changed line should be directly related to the user's request.

Clean up only unused imports, variables, functions, or files introduced by your own changes.

## 4. Goal-Driven Execution

Turn tasks into verifiable goals.

Examples:

- "Fix the bug" means identify or reproduce the bug, fix it, and verify the fix.
- "Add validation" means invalid input fails and valid input still works.
- "Refactor" means behavior remains unchanged and checks still pass.
- "Add feature" means the new behavior works through the intended interface.

For multi-step tasks, use a brief plan:

1. Inspect relevant code.
2. Make the minimal change.
3. Verify with the smallest meaningful check.

Run relevant verification when available:

- tests
- typecheck
- lint
- build
- targeted manual command

Do not claim verification passed unless it actually ran.

If verification cannot be run, say why and describe the risk.

## Final Response

When done, respond with:

### Changed
- What changed.

### Verified
- What command/check was run.
- Whether it passed.

### Notes / Risks
- Assumptions.
- Anything not verified.
- Related issues found but not changed.
