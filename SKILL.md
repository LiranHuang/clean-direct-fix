---
name: "clean-direct-fix"
description: "Repair code, config, prompts, policies, and runtime wiring through one trustworthy canonical path"
---

# Clean Direct Fix (V2)

Use this skill before repairing or optimizing code, configuration, prompts, policy text, data flow, or runtime wiring. Replace the bad path with one trustworthy owner instead of stacking new logic on top.

This skill owns concrete repair mechanics. Project goals, worktree strategy, approval boundaries, and parent continuation remain with their canonical engineering or orchestration owners.

## 1. State The Repair Contract

Before editing, state briefly:

1. **Repair philosophy:** no patch-on-patch, broad catch-all heuristics, fallback-heavy fixes, or parallel owners for one behavior.
2. **Canonical owner:** the one function, field, config key, prompt block, service, or data path that should own the behavior after repair.
3. **Bad or obsolete path:** the broken, duplicated, deprecated, or conflicting path being replaced, removed, or archived.
4. **Unaffected paths:** adjacent behavior, data, services, or user-visible flows that must remain unchanged.

If the canonical owner is unclear, inspect first. Do not add a fallback to avoid understanding the system.

## 2. Repair Through One Main Path

- Fix the source of truth, not only the symptom, renderer, or display layer.
- Rewrite or extend the existing canonical owner instead of creating a sibling owner.
- Centralize constants, budgets, thresholds, and routing rules; remove scattered hard-coded variants.
- Do not let one semantic fact enter a prompt or model through multiple fields.
- Keep renderers pure: read canonical state and render it without inventing business policy.
- Keep write and maintenance layers responsible for merge, dedupe, provenance, archive, audit, and lifecycle.
- Name the existing runtime owner before adding a scheduler, timer, cron, service, watcher, or runner.
- Integrate with existing lifecycle hooks unless an explicit privilege, scheduling, failure-isolation, or user-requested boundary requires a separate runtime.
- Remove or archive stale paths when the replacement is verified; prefer recoverable archive or trash over destructive deletion.
- Bound the blast radius. Do not change unrelated paths merely because they are nearby.

## 3. Enforce The Duplicate-Semantic Gate

Before editing prompt, config, policy, routing, or runtime text, search the target surface for repeated labels and repeated semantic responsibilities.

When an existing line, function, field, branch, or prompt block already owns the meaning:

1. select that canonical owner;
2. merge the new requirement into it;
3. delete or rewrite stale siblings;
4. add a positive assertion for the required behavior;
5. add a negative or count assertion proving duplicate owners are absent.

Repeated labels are valid only when the schema explicitly models them as list entries or separate scoped owners.

## 4. Reject “Just Add A Line” Repairs

For prompt, policy, config, routing, and renderer changes, adding explanatory text is suspicious by default. Before adding it, answer:

- Which existing owner already holds this semantic responsibility?
- Why can that owner not be rewritten?
- Which old text, field, function, or path will be removed or superseded?

If nothing is replaced, removed, or deliberately superseded, reject the change unless it is a bounded compatibility shim.

## 5. Bound Compatibility And Migration

A compatibility shim is allowed only when it records:

- owner;
- purpose;
- supported old and new surfaces;
- removal condition;
- verification proving it does not become a second source of truth.

Do not leave old and new implementations active for the same behavior. Migrate callers, configuration, tests, and runtime entrypoints to the canonical owner, then remove or archive the old path when safe.

## 6. Verify The Real Entry Path

Before claiming completion:

- inspect the diff for old and new paths coexisting;
- run the smallest meaningful compile, test, lint, build, or health check through the real entry path;
- run targeted positive checks for the required behavior;
- run negative or count checks for duplicate labels, fields, functions, config keys, services, timers, or runners;
- inspect that stale siblings and obsolete entrypoints are absent or intentionally archived;
- verify every process that can load the changed path is using the verified version;
- verify the canonical service or daemon owns runtime lifecycle after the repair;
- confirm temporary validation runners and artifacts were removed or explicitly retained;
- check for unrelated churn, secrets, and dirty configuration writes.

A local edit or passing substitute-path test is not completion when the real entry path still loads stale behavior.

## 7. Report Concisely

Return:

- **Main path:** the canonical owner now responsible.
- **Removed or superseded path:** stale siblings removed, merged, archived, or intentionally retained with a removal condition.
- **Verification:** exact diff, test, build, lint, health, positive, and negative/count checks run.
- **Remaining risk:** stale path, compatibility shim, unverified edge, or `none known`.

See [references/checklist.md](references/checklist.md) for the portable execution checklist and [references/source-notes.md](references/source-notes.md) for provenance and scope.
