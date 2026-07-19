# Backend Standards

Use these standards for any backend language or framework.

## Architecture

- Keep transport concerns at the edge: routes/controllers parse input, call application logic, and format output.
- Put business rules in services, use cases, commands, handlers, or domain modules.
- Put persistence behind repositories, gateways, model methods, or data-access modules according to the existing style.
- Keep cross-cutting concerns centralized: auth, validation, logging, error mapping, configuration.
- Use dependency injection or explicit construction when it improves testing and clarity; avoid abstract factories for simple code.

## Modularity

- Modules should have one reason to change.
- Public APIs between modules should be small and named after domain behavior, not database details.
- Avoid circular dependencies. If two modules need each other, extract shared domain concepts or invert one dependency.
- Keep file names, folder names, and test placement consistent with the repo.

## Reuse, KISS, And DRY

- Prefer simple duplication over premature abstraction when there are only two small call sites with uncertain direction.
- Extract shared code when duplication has the same meaning, same lifecycle, and same likely future changes.
- Reuse installed framework/library features before writing custom infrastructure.
- Delete dead code instead of preserving backup files, commented blocks, or unused wrappers.
- Avoid pass-through layers that only rename a single function without adding policy, validation, or isolation.

## Validation And Errors

- Validate inputs at boundaries: HTTP requests, jobs, message consumers, CLI commands.
- Keep internal functions typed or contract-checked where the language supports it.
- Return stable error shapes to clients; log detailed internal causes server-side.
- Do not leak secrets, stack traces, or private data in user-facing errors.

## Testing

- Cover business rules with unit tests.
- Cover data access and migrations with integration tests when practical.
- Cover critical HTTP flows with request-level tests.
- Add regression tests for bugs and high-risk refactors.

## Review Smells

- business logic inside route handlers or UI-facing controllers;
- services that depend directly on HTTP request/response objects;
- duplicate utilities for dates, validation, retries, auth, or formatting;
- unused exports, old files, commented-out implementations;
- large modules mixing validation, orchestration, SQL, and formatting;
- new dependency added for one trivial helper.
