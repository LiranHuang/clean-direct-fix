---
name: clean-direct-fix
description: Repair a known configuration, prompt, policy, routing, or runtime-wiring defect through one canonical path. Use directly when the cause is known, or after diagnose resolves it; code changes use start-to-code.
---

# Clean Direct Fix

Use for an authorized non-code repair whose main risk is adding a workaround
beside the broken behavior. For an unknown cause, investigate with `diagnose`
first; an already authorized repair needs no renewed permission at the transition.
Applicable host engineering instructions and `AGENTS.md` govern lifecycle, Git,
deployment and acceptance.

Name the canonical owner, obsolete or conflicting path, adjacent behavior to
preserve, and observable repaired result. Trace the real load or routing path
when ownership is unclear.

Change the source of truth, not only its symptom or consumer. Consolidate
duplicate labels, keys, prompt blocks, routes, loaders, runners, thresholds, and
policies under one owner. A compatibility shim needs proven callers, one
subordinate source of truth, and a removal condition.

A root-cause repair must explain and change the evidenced mechanism producing
the reported error, not merely prevent a downstream consumer from accepting its
output. Suppression, filtering, deduplication, retries and policy guards are
mitigation unless evidence places the defect at that boundary. If the producing
mechanism is unknown, report it as unresolved; never relabel mitigation as a
root-cause fix. Make this distinction within the existing owner tracing and diff
review, without an additional audit, test gate or speculative upstream search. Retain a safeguard only for a current requirement,
contract boundary or concrete failure mode; preserve necessary access control,
input validation, integrity and recovery. In the existing final diff inspection,
remove unjustified mechanisms and duplicated checks; add no separate audit.

After the repair, accept the requested behavior through the smallest existing
real entry path, including actual loading when runtime changed, then stop.
Do not default to tests, probes, fixtures, hashes, smoke or separate positive/
negative gates; add only evidence missing for acceptance. Diagnose beforehand
only to unblock the repair; after a fix, recheck only affected failed evidence. Report the canonical path, retired or retained path,
focused verification, and remaining risk.

For a complex, multi-surface, or high-risk repair, read the
[repair checklist](references/repair-checklist.md). Do not load it for a simple
one-owner correction.
