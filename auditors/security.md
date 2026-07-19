# Security Auditor

Use with `references/security.md`.

Inspect:

1. Secrets: keys, tokens, passwords, private keys, credentials, committed env files.
2. Authentication: session/token expiry, secure storage, middleware coverage.
3. Authorization: server-side checks for read, write, delete, admin, tenant/org boundaries.
4. Injection: SQL, command, template, HTML, unsafe deserialization.
5. Validation: external inputs from HTTP, forms, jobs, webhooks, file uploads.
6. Dependency risk: package audit results when available.
7. Data exposure: PII/secrets in responses, logs, analytics, errors.
8. Browser security: XSS, CSRF, CORS, unsafe HTML rendering.

Typical findings:

- `secret-in-code`
- `missing-authz`
- `injection-risk`
- `missing-input-validation`
- `unsafe-token-storage`
- `pii-in-logs`
- `vulnerable-dependency`
- `unsafe-cors`
