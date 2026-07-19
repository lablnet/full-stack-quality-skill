# Full-Stack Quality Rule

Apply this rule when working on database, backend, frontend, HTTP API, GraphQL, security, testing, performance, observability, delivery/configuration, or utility/library code.

## Review Mode

- Audits and reviews are read-only.
- Do not edit code, migrations, schemas, configs, docs, generated files, or lockfiles unless the user explicitly asks for implementation or document generation.
- Include evidence for findings: file path, line or symbol when available, observed behavior, impact, recommendation, and validation.

## Output

- Markdown for human review reports, ADRs, and implementation plans.
- JSON for structured findings.
- YAML only when required by an existing project/tool or requested by the user.

## Standards

- Database: normalization, constraints, keys, indexes, migrations.
- Backend: thin transport handlers, modular services/use cases, data access boundaries, KISS, DRY, dead-code removal.
- Frontend: UI consistency, accessibility, responsive behavior, and framework-specific logic placement.
- HTTP API: correct methods, resource URLs, status codes, validation, error envelopes.
- GraphQL: schema clarity, thin resolvers, server-side authz, N+1 prevention, pagination.
- Security: secrets, auth, injection, dependency risk, sensitive data exposure.
- Utilities: duplicate helpers, needless wrappers, library reuse, dead exports.
- Testing, performance, observability, and delivery/configuration: check when relevant.
