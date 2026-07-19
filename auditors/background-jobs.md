# Background Jobs Auditor

Use with `references/background-jobs.md`.

Inspect workers, queues, cron, retries, idempotency, dead letters, batch sizes, state tracking, alerts, and job metrics.

Typical findings: `non-idempotent-retry`, `silent-job-failure`, `missing-dead-letter`, `unbounded-job-batch`, `hidden-cron`.
