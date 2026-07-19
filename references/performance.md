# Performance Standards

Use these standards for backend, database, frontend, and API performance.

## Defaults

- Prefer clarity first, then optimize measured bottlenecks.
- Fix obvious structural problems early: N+1 queries, unbounded lists, large payloads, repeated expensive renders, synchronous long-running work.
- Add caching only with clear invalidation rules.
- Keep pagination, filtering, and sorting explicit.

## Backend And Database

- Use indexes for frequent filters, joins, and ordering.
- Avoid loading entire tables or full object graphs for list views.
- Batch external calls and database queries when safe.
- Move long-running work to background jobs when request latency would suffer.
- Use transactions around complete business operations.

## Frontend

- Avoid unnecessary global state updates that re-render large trees.
- Split large bundles according to route or feature when the project supports it.
- Keep images/media appropriately sized.
- Avoid expensive computations in render paths; memoize only when it solves a real issue.

## HTTP

- Paginate list endpoints.
- Avoid over-fetching sensitive or heavy fields.
- Use compression and cache headers where appropriate.
- Use idempotency for retryable side-effect requests.

## Review Smells

- list endpoint without pagination;
- repeated query inside a loop;
- large JSON payload for a small UI need;
- expensive frontend work during every render;
- cache without invalidation;
- synchronous request doing slow external work.
