# Observability Auditor

Use with `references/observability.md`.

Inspect:

1. Error handling and whether errors are swallowed.
2. Logging in request handlers, jobs, external calls, and important domain events.
3. Sensitive data in logs.
4. Request/correlation IDs.
5. Metrics for critical flows.
6. Alerting or failure visibility for background jobs and scheduled tasks.
7. Client-side error reporting when there is a frontend.

Typical findings:

- `swallowed-error`
- `missing-contextual-log`
- `sensitive-data-in-log`
- `missing-correlation-id`
- `missing-critical-metric`
- `silent-job-failure`
