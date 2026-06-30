---
name: strideworkers
description: Stride Workflow skill for token-aware worker selection. Use when deciding default, balance, or heavy worker mode.
---

# Stride Workers

Use this skill when deciding how much worker support a task deserves.

## Use when

- The user asks about worker strategy.
- You need to choose between default, balance, and heavy modes.
- You want to keep token use under control without losing the main workflow.

## Do

- Start with the smallest useful mode.
- Use the main thread as orchestrator, at least one `stridebuilder` as the editing worker, `stridelead` as the recon worker when needed, and at least one `stridereviewer` as the review worker by default.
- Add probe or debug support only when the task justifies it.
- Keep tiny changes on the lightest path.

## Modes

- `default`: main chat orchestrates, one `stridebuilder` edits, and one `stridereviewer` checks the diff
- `balance`: default plus `stridelead` recon or one extra probe/debug helper when needed; may split the scope across more than one builder/reviewer pair if that is cleaner
- `heavy`: `stridelead` recon plus multiple builders, multiple reviewers, and extra probe/debug support for broad or risky work
