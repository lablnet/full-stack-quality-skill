# Analytics Standards

Use for product analytics, event tracking, funnels, experiments, and telemetry.

- Events should have an owner, purpose, stable name, and documented schema.
- Avoid duplicate events for the same user action.
- Do not send secrets, tokens, raw PII, or excessive free-form text.
- Track critical funnels consistently across frontend/backend when needed.
- Keep experiment flags and analytics definitions aligned.

Review smells: event spam, inconsistent names, PII in event properties, no funnel coverage for critical flow, stale experiment events.
