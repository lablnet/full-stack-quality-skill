# AGENTS.md

Use the `full-stack-quality` skill when reviewing, designing, or implementing database, backend, frontend, HTTP API, GraphQL, security, testing, performance, observability, delivery/configuration, or utility/library work.

## Required Behavior

- Review/audit mode is read-only.
- Do not edit code, schemas, migrations, configs, docs, generated files, or lockfiles unless the user explicitly asks for implementation or document generation.
- Inspect existing conventions before recommending changes.
- Prefer the smallest change that improves correctness, clarity, maintainability, security, or consistency.
- Do not introduce dependencies, frameworks, services, or abstractions unless they remove real complexity.
- Include evidence for findings: path, line or symbol when available, observed behavior, and impact.
- Use Markdown for human reports and JSON for structured findings.

## Review Areas

- Database: normalization, keys, constraints, indexes, migrations, data access.
- Backend: layers, modularity, reuse, KISS, DRY, dead code, validation, tests.
- Frontend: framework-specific logic placement, components, design consistency, accessibility, responsive behavior.
- HTTP API: methods, URLs, status codes, validation, error shape, authz.
- GraphQL: schema, resolvers, authz, N+1 prevention, pagination, generated types.
- Security: secrets, authn/authz, injection, dependency risk, data exposure.
- Utilities: duplicate helpers, unnecessary wrappers, library reuse, dead exports.
- Testing: critical paths, regression tests, brittle/flaky tests.
- Performance: N+1, unbounded lists, payload size, expensive renders, caching.
- Observability: logs, metrics, traces, alerting, safe errors.
- Delivery: config, CI/CD, deploy safety, migrations, feature flags.
