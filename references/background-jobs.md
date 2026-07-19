# Background Jobs Standards

Use for queues, workers, cron, scheduled tasks, imports, exports, webhooks, and async processing.

- Jobs should be idempotent or safely deduplicated.
- Define retry policy, timeout, dead-letter/failure behavior, and alerting.
- Persist enough state to resume or inspect failures.
- Avoid unbounded batch sizes.
- Make schedules visible and environment-aware.

Review smells: retry causes duplicate side effects, silent job failure, no dead-letter handling, cron hidden outside repo, long job blocks web request, no job metrics.
