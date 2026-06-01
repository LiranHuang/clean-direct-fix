---
name: canonical-repair-discipline
description: Packages a generic clean repair discipline for code, config, prompt, and runtime fixes: one canonical owner, no patch-on-patch repairs, no fallback-heavy heuristics, and duplicate-semantic gates. Use when repairing bugs, refactoring prompt/config/runtime text, consolidating duplicated behavior, reviewing fixes, or preparing a reusable repair checklist without applying it automatically.
---

# Canonical Repair Discipline

Use this skill when a repair or optimization risks becoming patch-on-patch work. The goal is to replace bad paths with one trustworthy owner, not to add more branches, fallbacks, or explanatory lines.

## Pre-edit contract

Before editing code, config, prompts, runtime wiring, or policy text, state:

1. **Repair philosophy:** no patch-on-patch, no fallback-heavy catch-all heuristics, no “just add one line” fixes, no parallel owners for one behavior.
2. **Canonical owner:** the one function, field, config key, prompt block, service, or data path that should own the behavior.
3. **Bad/obsolete path:** the broken, duplicated, deprecated, or conflicting path being replaced, removed, or archived.
4. **Unaffected paths:** adjacent behavior that must remain unchanged.

If the canonical owner is unclear, inspect first. Do not add a fallback to avoid understanding the system.

## Core rules

- Fix the source of truth, not only the renderer, display, or symptom.
- Replace or rewrite the existing owner instead of adding a sibling owner.
- Remove/archive stale paths immediately when safe; prefer recoverable archive over destructive deletion.
- Temporary compatibility shims require owner, purpose, and removal condition.
- Keep renderers pure: render canonical state; do not invent business rules there.
- Keep write/maintenance layers responsible for merge, dedupe, provenance, audit, and lifecycle.
- For daemon/runtime features, name the existing runtime owner before adding a scheduler, timer, cron, service, or runner. If the main daemon already has lifecycle hooks, integrate start/stop there instead of creating a parallel lifecycle, unless the user explicitly requested isolation or a real privilege/scheduling/failure-isolation boundary requires it.
- Bound the blast radius; do not alter unrelated flows just because they are nearby.

## Duplicate-semantic gate

For prompt/config/runtime/policy text, identify repeated labels and repeated semantic responsibilities before editing.

Do not add another line for a new edge case when an existing line/function/field owns that meaning. Instead:

1. choose the canonical owner;
2. merge the new edge case into that owner;
3. delete or rewrite stale sibling text/path;
4. add positive and negative/count checks proving the owner is present exactly once.

Labels such as `usage`, `instructions`, `rules`, `policy`, `context`, `notes`, `warning`, `使用说明`, `规则`, or domain-specific section names should appear once unless explicitly modeled as list entries.

## Verification gate

Before claiming completion:

- inspect the diff for old/new paths coexisting;
- run the smallest meaningful compile/test/lint/build/health check;
- for prompt/config/policy changes, run positive presence checks and negative/count checks for duplicate labels or semantic owners;
- grep or otherwise inspect that stale sibling labels/functions/fields/paths/services/timers/runners are gone;
- verify runtime continuity for every process that can load the changed path;
- for runtime lifecycle repairs, verify the canonical service/daemon owns the behavior and obsolete timers/services/runners are disabled or absent;
- check for unrelated churn, secrets, and dirty config writes.

## Final report

Use concise bullets:

- **Main path:** canonical owner now responsible.
- **Removed/obsolete path:** stale sibling labels/functions/fields/paths removed, merged, archived, or intentionally retained with reason.
- **Verification:** exact diff/test/build/lint/health/count checks run.
- **Remaining risk:** fallback, stale path, unverified edge, or “none known”.

See [references/checklist.md](references/checklist.md) for a portable checklist and [references/source-notes.md](references/source-notes.md) for provenance.
