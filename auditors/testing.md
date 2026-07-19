# Testing Auditor

Use with `references/testing.md`.

Inspect:

1. Test commands, frameworks, fixtures, factories, and CI checks.
2. Critical paths: auth, payments/orders, data mutations, imports/exports, admin actions.
3. Backend service/use-case coverage.
4. Database migration and data-access coverage.
5. HTTP validation/status/error coverage.
6. Frontend form, accessibility, loading/error/empty state coverage.
7. Flaky, skipped, brittle, or implementation-detail-heavy tests.

Typical findings:

- `missing-critical-test`
- `missing-regression-test`
- `brittle-test`
- `flaky-test`
- `missing-api-contract-test`
- `missing-migration-test`
