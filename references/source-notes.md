# Source notes

Clean Direct Fix V2 consolidates the public `canonical-repair-discipline` package with durable generic improvements proven in the local `clean-direct-fix` workflow.

Retained general lessons:

- A fix that only appends text can create semantic debt even when the new text is correct.
- Existence tests are insufficient for prompt, config, and policy repair; negative and count assertions are also required.
- Constants, budgets, thresholds, and routing rules need one owner.
- Compatibility paths need an explicit removal condition and must not become a second source of truth.
- Runtime verification must cover every process that can still load the old path.
- Runtime behavior should remain under the existing lifecycle owner unless a real boundary justifies isolation.

Excluded from the public package:

- product-specific schemas and prompt fields;
- local usernames, paths, service names, and account identifiers;
- deployment-specific OpenClaw configuration procedures;
- project-specific migration state or temporary compatibility rules.

Those concerns belong in project-owned skills, configuration, or documentation rather than this reusable repair procedure.
