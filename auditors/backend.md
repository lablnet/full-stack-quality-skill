# Backend Auditor

Use with `references/backend.md`.

Inspect:

1. Entry points: routes/controllers/jobs/commands.
2. Layering: transport, validation, business logic, persistence, integrations.
3. Reuse: duplicated utilities, repeated business rules, copy-paste handlers.
4. KISS: needless wrappers, excessive factories, abstractions with one implementation.
5. Dead code: unused exports, old files, commented blocks, unreferenced modules.
6. Error handling: consistent mapping, internal logging, safe client messages.
7. Tests: business rules, data access, HTTP flows, regression coverage.

Typical findings:

- `thick-controller`
- `business-logic-in-transport`
- `data-access-leak`
- `copy-paste-duplicate`
- `needless-abstraction`
- `dead-code`
- `missing-critical-test`
