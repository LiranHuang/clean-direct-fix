# Clean Direct Fix

A portable OpenClaw skill for repairing code, configuration, prompts, policies, data flow, and runtime wiring through one trustworthy canonical path.

It prevents patch-on-patch fixes, fallback-heavy heuristics, duplicate semantic owners, and old/new implementations remaining active together.

## Core capabilities

- Names one canonical owner before editing.
- Replaces the bad path instead of adding a parallel path.
- Centralizes duplicated constants, budgets, thresholds, and routing rules.
- Requires positive checks plus negative/count checks for duplicate semantics.
- Keeps compatibility shims bounded by owner and removal condition.
- Verifies the real runtime entry path and removes temporary validation artifacts.

## Install

```bash
openclaw skills install \
  git:LiranHuang/clean-direct-fix \
  --global
```

Then add `clean-direct-fix` to the intended agent skill allowlist.

## Use it for

- bug fixes and refactors;
- prompt or policy repairs;
- configuration consolidation;
- duplicate routing or renderer cleanup;
- runtime lifecycle repairs;
- migration from obsolete implementations to one canonical path.

This skill owns concrete repair mechanics. It does not replace project planning, approval policy, worktree strategy, or parent-task orchestration.

## Package

```text
SKILL.md
references/checklist.md
references/source-notes.md
```

`SKILL.md` is at the repository root so the repository can be installed directly as an OpenClaw skill package.
