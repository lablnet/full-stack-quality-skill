# Testing Standards

Use these standards for unit, integration, end-to-end, contract, migration, and visual/UI tests.

## Strategy

- Test behavior, not private implementation details.
- Focus coverage on business rules, critical user flows, security boundaries, migrations, and bug regressions.
- Prefer fast unit tests for pure rules, integration tests for database/framework behavior, and end-to-end tests for critical journeys.
- Keep tests deterministic. Avoid arbitrary sleeps, real external services, and order-dependent test data.

## What To Cover

- Backend: services/use cases, validation, authz, error mapping, data access behavior.
- Database: migrations, constraints, transactions, important query behavior.
- Frontend: user-visible behavior, forms, accessibility basics, loading/error/empty states.
- HTTP API: status codes, payload shapes, validation errors, permission checks.
- Security: authz gaps, injection prevention, sensitive field exposure.

## Review Smells

- tests only cover happy paths;
- brittle tests that assert internal structure instead of behavior;
- missing regression test for a fixed bug;
- end-to-end tests used where a unit/integration test would be simpler;
- mocked database for code whose risk is database behavior;
- skipped/flaky tests without an owner or reason.
