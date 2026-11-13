# Repair checklist

Use for complex, multi-surface, or high-risk repairs; do not load it for a simple one-owner local correction.

1. Name the canonical semantic owner, bad or obsolete path, unaffected adjacent behavior, and observable repair outcome.
2. Trace the real entry path, including callers, loaders, configuration precedence, generated copies, and runtime consumers that can affect the behavior.
3. Search for duplicate labels, fields, functions, configuration keys, prompt blocks, routes, services, timers, runners, or data paths with the same semantic responsibility.
4. Put the change in the canonical owner; centralize duplicated constants, thresholds, budgets, and routing rules there.
5. Remove, rewrite, or deliberately retire stale siblings after the replacement is verified. Do not leave old and new active for the same behavior.
6. For a compatibility or migration shim, record its owner, purpose, old/new surfaces, removal condition, and evidence it is not a second source of truth.
7. Migrate relevant callers, configuration, tests, and runtime entry points to the canonical owner.
8. Run the project's real entry-path validation for the repaired behavior.
9. Add or run positive evidence for the required behavior and negative or count evidence for stale or duplicate ownership where plausible.
10. For runtime-affecting changes, verify each relevant process or loader uses the intended version or configuration.
11. Inspect the final delta for coexistence, unjustified switches/fallbacks/retries, repeated checks or hidden errors, unrelated churn, temporary artifacts, and secrets; retain necessary security and integrity safeguards.
12. Report the main path, retired or retained old path and its removal condition, exact verification, and remaining risk.
