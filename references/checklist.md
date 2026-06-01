# Canonical repair checklist

Use this checklist for any code/config/prompt/runtime repair.

1. Name the canonical owner.
2. Name the bad/obsolete path.
3. Name unaffected paths.
4. For daemon/runtime behavior, name the existing lifecycle owner before adding any scheduler, timer, cron, service, or runner.
5. Search for sibling labels/functions/fields/config keys/prompt blocks with the same semantic responsibility.
6. Rewrite the owner instead of adding a new sibling.
7. Remove/archive stale siblings, including temporary external runners used for validation.
8. Add or run a positive assertion that the required behavior/text exists.
9. Add or run a negative/count assertion that duplicate labels/semantic owners do not exist.
10. Inspect diff for old/new coexistence and unrelated churn.
11. Run the smallest meaningful compile/test/lint/build/health check.
12. If runtime code changed, verify every relevant process/service actually loaded the new path.
13. If lifecycle ownership changed, verify obsolete timers/services/runners are disabled or absent.
14. Final report: main path, removed obsolete path, verification, remaining risk.
