# Performance Auditor

Use with `references/performance.md`.

Inspect:

1. Database query patterns, N+1 loops, missing pagination, missing indexes.
2. Backend request paths doing slow synchronous work.
3. Repeated external calls that could be batched or cached.
4. API payload size and over-fetching.
5. Frontend render hot spots, expensive derived values, oversized bundles/media.
6. Cache usage and invalidation rules.

Typical findings:

- `n-plus-one-query`
- `unbounded-list`
- `missing-performance-index`
- `slow-sync-request`
- `large-payload`
- `expensive-render`
- `unsafe-cache`
