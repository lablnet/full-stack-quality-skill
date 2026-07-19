# HTTP API Standards

Use these standards for REST-like APIs and HTTP endpoints, regardless of backend language.

## Methods

- `GET`: read a resource; safe and cacheable when possible.
- `POST`: create a resource or run a non-idempotent command.
- `PUT`: replace a resource or create at a known URI; idempotent.
- `PATCH`: partially update a resource; document patch semantics.
- `DELETE`: remove or archive a resource; idempotent behavior is preferred.

## URLs

- Use resource nouns, not verbs: `/users/{id}/orders`, not `/getUserOrders`.
- Keep nesting shallow. Prefer query filters for search/listing.
- Version APIs intentionally when client compatibility requires it.
- Use consistent path parameter names: `{user_id}` or `{userId}`, matching project style.

## Status Codes

- `200 OK`: successful read/update with body.
- `201 Created`: resource created; include location or created representation.
- `202 Accepted`: async work accepted but not complete.
- `204 No Content`: successful action without response body.
- `400 Bad Request`: malformed request or invalid syntax.
- `401 Unauthorized`: missing/invalid authentication.
- `403 Forbidden`: authenticated but not allowed.
- `404 Not Found`: resource does not exist or must be hidden.
- `409 Conflict`: version, uniqueness, or state conflict.
- `422 Unprocessable Content`: well-formed request with semantic validation errors, if the project uses it.
- `429 Too Many Requests`: rate limited.
- `500`: unexpected server error.

## Payloads

- Validate and document request bodies, query params, and path params.
- Use consistent casing in JSON keys across the API.
- Prefer stable error envelopes, for example:

```json
{
  "error": {
    "code": "validation_failed",
    "message": "One or more fields are invalid.",
    "fields": {
      "email": "Must be a valid email address."
    }
  }
}
```

## Reliability

- Make retries safe with idempotency keys for payment, order, import, and external side-effect endpoints.
- Use pagination for list endpoints.
- Define sorting and filtering rules explicitly.
- Avoid returning secret, internal, or excessive fields.
- Keep authorization checks server-side even when the frontend hides actions.

## Review Smells

- `POST` used for every action;
- endpoints named after implementation methods instead of resources;
- inconsistent status codes for the same outcome;
- validation errors returned as plain strings in some routes and objects in others;
- list endpoints without pagination;
- authorization done only in the frontend.
