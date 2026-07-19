# Project Docs Index

Use this as the entry point for future agents and developers.

## Read First

- `architecture.md`: target architecture and boundaries.
- `decisions.md`: accepted ADRs and trade-offs.
- `security.md`: security rules and known risks.
- `testing.md`: required tests and critical paths.
- `migration-backlog.md`: known gaps and cleanup plan.
- `audit/inventory.json`: latest health score and trend.
- `audit/drift-report.md`: docs-vs-code mismatches.

## Rules For New Work

- Follow the target architecture.
- Do not add new dependencies without a decision.
- Update docs when architecture, API, schema, security, or UI conventions change.
- Add tests for touched critical paths.
- Do not expand legacy exceptions; reduce them when practical.

## Definition Of Done

- Code follows the target layer/module boundaries.
- Relevant tests pass or missing tests are explicitly called out.
- Security and auth rules are respected.
- API/GraphQL/database changes are documented.
- Drift report has no new critical/high mismatch.
