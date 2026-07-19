# Review Findings Template

Use this format for audits and code reviews.

Audit/review mode is read-only. This report may recommend changes, but it must not imply changes were made unless the user explicitly asked for implementation.

## Findings

### [severity] Title

- Area: database | backend | frontend | http_api | cross_stack
- Evidence: `path:line` - observed behavior
- Impact: why it matters
- Recommendation: smallest practical fix
- Validation: test, lint, typecheck, migration check, or manual verification

## Open Questions

- Question, only when a safe recommendation requires missing context.

## Summary

Short summary after findings, not before.

## Optional Structured Finding

Use JSON for machine-readable findings:

```json
{
  "id": "short-stable-id",
  "area": "backend",
  "severity": "medium",
  "title": "Route handler contains business logic",
  "evidence": [
    {
      "path": "src/routes/orders.ts",
      "line": 42,
      "detail": "Handler calculates totals and writes multiple tables inline."
    }
  ],
  "impact": "The behavior is difficult to reuse and test.",
  "recommendation": "Move order creation into a service/use-case.",
  "validation": "Add service tests and a request-level test."
}
```
