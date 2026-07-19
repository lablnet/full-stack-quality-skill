# Multi-Tenancy Auditor

Use with `references/multi-tenancy.md`.

Inspect tenant/org/workspace scoping in queries, mutations, jobs, exports, caches, permissions, indexes, and admin tools.

Typical findings: `missing-tenant-scope`, `client-trusted-tenant-id`, `cross-tenant-cache-key`, `tenant-unique-constraint-missing`, `unsafe-cross-tenant-admin`.
