# HTTP API Auditor

Use with `references/http-api.md`.

Inspect:

1. Method semantics: GET, POST, PUT, PATCH, DELETE.
2. URL shape: resource nouns, nesting, parameter naming, versioning.
3. Status codes: consistency across success, validation, auth, conflict, and server errors.
4. Payloads: request validation, response casing, error envelope.
5. Auth: server-side checks, role/permission boundaries.
6. Reliability: pagination, idempotency, retries, async workflows.
7. Data exposure: secret/private/internal fields in responses.

Typical findings:

- `wrong-http-method`
- `verb-based-url`
- `inconsistent-status-code`
- `missing-input-validation`
- `inconsistent-error-shape`
- `missing-server-authz`
- `unpaginated-list-endpoint`
