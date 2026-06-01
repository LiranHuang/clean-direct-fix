# Canonical Repair Discipline

A portable OpenClaw skill for clean optimization and repair work.

The skill enforces one canonical owner for each behavior, avoids patch-on-patch fixes, rejects fallback-heavy repairs, and requires duplicate-semantic checks for code, config, prompt, runtime, and policy changes.

## Contents

```text
SKILL.md
references/checklist.md
references/source-notes.md
```

`SKILL.md` is intentionally placed at the repository root so the repository can be used directly as the skill package root.

## Core philosophy

- Replace bad paths with one trustworthy owner.
- Do not stack new fallback logic on top of broken logic.
- Rewrite existing semantic owners instead of adding sibling owners.
- Remove or archive obsolete paths immediately when safe.
- For runtime features, use the existing daemon/service lifecycle when it already owns the behavior; avoid parallel timers/services/runners unless a real boundary justifies them.
- Verify with positive checks plus negative/count checks that duplicate owners are absent.

## Status

Local repository only. Remote origin is intentionally not configured yet.
