# Utilities And Libraries Auditor

Use with `references/utilities.md`.

Inspect:

1. Duplicate helpers with the same purpose.
2. Helpers that duplicate built-in language, framework, or installed package features.
3. Utility folders that mix unrelated domain logic.
4. Pass-through wrappers that add no policy or testability.
5. Dead utility exports with no references.
6. Helpers with hidden side effects or global state.
7. Missing tests for utilities that handle money, time, permissions, parsing, security, or business rules.

Typical findings:

- `duplicate-utility`
- `reinvented-library-feature`
- `utility-junk-drawer`
- `needless-wrapper`
- `dead-utility`
- `side-effectful-helper`
- `missing-utility-test`
