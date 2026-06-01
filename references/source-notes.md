# Source notes

This generic package was derived from the local `clean-direct-fix` repair philosophy without modifying or replacing that original skill.

Generalized lessons:

- A fix that only appends text can create semantic debt even if the new sentence is true.
- Existence tests are insufficient for prompt/config/policy repair; count and negative assertions are required.
- Duplicate semantic owners should be rejected at review time, not hidden by display fallbacks.
- Runtime verification must cover every process that can still load the old code path.
- Daemon/runtime features should live under the existing service lifecycle when one already owns the behavior; external timers, cron jobs, services, or manual runners need explicit boundary justification and must be removed after temporary validation.

This package intentionally avoids project-specific references and is not automatically applied to any agent allowlist or system prompt layer.
