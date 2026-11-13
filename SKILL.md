---
name: clean-direct-fix
description: Repair a known configuration, prompt, policy, routing, or runtime-wiring defect through one canonical path. Use after the cause is known; repository code changes use start-to-code.
---

# Clean Direct Fix

Use for an authorized non-code repair whose main risk is adding a workaround
beside the broken behavior. `AGENTS.md` governs lifecycle, Git, deployment, and
acceptance.

Name the canonical owner, obsolete or conflicting path, adjacent behavior to
preserve, and observable repaired result. Trace the real load or routing path
when ownership is unclear.

Change the source of truth, not only its symptom or consumer. Consolidate
duplicate labels, keys, prompt blocks, routes, loaders, runners, thresholds, and
policies under one owner. A compatibility shim needs proven callers, one
subordinate source of truth, and a removal condition.

Fix the cause rather than masking it with extra switches, fallback routes,
retries or policy layers. Retain a safeguard only for a current requirement,
contract boundary or concrete failure mode; preserve necessary access control,
input validation, integrity and recovery. In the existing final diff inspection,
remove unjustified mechanisms and duplicated checks; add no separate audit.

Verify the required behavior and, when duplication is plausible, the absence or
count of obsolete owners. If runtime is affected, prove the real loader uses the
adopted configuration. Report the canonical path, retired or retained path,
focused verification, and remaining risk.

For a complex, multi-surface, or high-risk repair, read the
[repair checklist](references/repair-checklist.md). Do not load it for a simple
one-owner correction.
