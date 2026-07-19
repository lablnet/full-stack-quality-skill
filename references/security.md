# Security Standards

Use these standards for backend, frontend, database, infrastructure-adjacent config, and HTTP APIs.

## Secrets And Configuration

- Never commit API keys, tokens, passwords, private keys, or production connection strings.
- Keep secrets in the platform's secret manager or environment configuration.
- Do not log secrets, auth headers, reset tokens, one-time codes, or full payment/PII values.
- Use separate development, staging, and production configuration.

## Authentication And Authorization

- Authentication proves who the user is; authorization proves what they may do.
- Authorization checks must happen server-side, even if the frontend hides controls.
- Centralize permission checks through policies, guards, middleware, decorators, or service-level checks.
- Treat tenant/org/project ownership as part of authorization.
- Sessions and tokens need expiry, rotation strategy, and secure storage.

## Input And Output Safety

- Validate all external input: HTTP bodies, query params, path params, file uploads, webhooks, jobs, and CLI args.
- Parameterize SQL and command execution.
- Escape or sanitize output according to context: HTML, SQL, shell, URL, CSV, logs.
- Avoid unsafe deserialization.
- Return only fields the client needs.

## Dependency And Supply Chain

- Prefer maintained libraries with active security fixes.
- Do not add packages for trivial helpers.
- Run the project's dependency audit tool when security is in scope.
- Pin or lock dependencies according to the project's package manager.

## Frontend Security

- Do not store long-lived sensitive tokens in localStorage unless the architecture explicitly accepts that risk.
- Avoid `dangerouslySetInnerHTML`, raw HTML injection, or template bypasses without sanitization.
- Keep CSRF protections aligned with the auth model.
- Do not expose hidden admin data in client payloads and rely on UI hiding.

## Review Smells

- hardcoded secret-looking strings;
- CORS wildcard in production;
- SQL or shell string concatenation;
- missing authz checks on update/delete/admin endpoints;
- PII or tokens in logs;
- dependency with known high/critical vulnerability;
- sensitive fields returned to the frontend.
