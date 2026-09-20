# Clean direct fix checklist

Use this checklist for code, config, prompt, policy, data-flow, or runtime repairs.

1. Name the canonical owner.
2. Name the bad or obsolete path.
3. Name adjacent paths that must remain unchanged.
4. Search for sibling labels, functions, fields, config keys, prompt blocks, routes, services, and runners with the same semantic responsibility.
5. Rewrite or extend the canonical owner instead of adding a sibling.
6. Centralize duplicated constants, budgets, thresholds, and routing rules.
7. Remove or archive stale siblings after the replacement is verified.
8. Give every compatibility shim an owner, purpose, and removal condition.
9. Run a positive assertion for the required behavior.
10. Run a negative or count assertion proving duplicate semantic owners are absent.
11. Inspect the diff for old/new coexistence and unrelated churn.
12. Run the smallest meaningful check through the real entry path.
13. Verify every relevant process or service loaded the verified version.
14. Remove temporary validation runners and artifacts unless explicitly retained.
15. Report the main path, removed path, verification, and remaining risk.
