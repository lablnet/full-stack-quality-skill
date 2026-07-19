# Observability Standards

Use these standards for logs, metrics, traces, alerting, and error reporting.

## Logging

- Log meaningful events at boundaries: request start/end when appropriate, job execution, external calls, important domain transitions.
- Include correlation/request IDs when the stack supports it.
- Do not log secrets, tokens, full PII, payment data, or raw credentials.
- Use structured logs where the project supports them.

## Errors

- Map internal errors to safe client-facing messages.
- Preserve cause/context for debugging in server logs or error tracking.
- Do not swallow errors silently.
- Include enough context to debug without exposing sensitive data.

## Metrics And Alerts

- Important flows should expose success/failure counts, latency, queue depth, and external dependency failures when practical.
- Alerts should map to user impact or operational risk.
- Avoid alerting on noise with no owner or action.

## Review Smells

- `console.log` or print debugging left in production paths;
- errors caught and ignored;
- logs contain tokens, passwords, or PII;
- no correlation between frontend error, backend request, and job/external call;
- critical background jobs fail silently;
- alert exists but no one knows what to do.
