# Multi-Tenancy Standards

Use when the product has tenants, organizations, workspaces, accounts, stores, teams, projects, or any scoped customer boundary.

- Every query, mutation, job, export, and admin action must enforce tenant scope.
- Tenant IDs should be explicit in data models and indexes where needed.
- Uniqueness rules must be tenant-aware when names/slugs/emails are scoped.
- Background jobs and webhooks must carry tenant context safely.
- Cross-tenant admin access needs explicit permission and auditability.

Review smells: missing tenant filter, global lookup by ID only, tenant ID trusted from client, cross-tenant cache key, export without tenant scope.
