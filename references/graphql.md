# GraphQL Standards

Use these standards only when the project uses GraphQL through Apollo, Yoga, Mercurius, Graphene, Strawberry, Hot Chocolate, Hasura, Prisma GraphQL, Relay, urql, Apollo Client, or similar tooling.

## Schema Design

- Model domain capabilities clearly with types, queries, mutations, inputs, enums, and payloads.
- Prefer explicit input types over large generic JSON arguments.
- Use nullable fields intentionally. In GraphQL, nullability is part of the contract.
- Keep naming consistent with the existing schema.
- Avoid exposing database tables directly when the domain API needs a safer or clearer shape.

## Queries And Mutations

- Queries read data and should not create side effects.
- Mutations change state and should return a useful payload: changed entity, user-facing errors, or operation status.
- Use stable error patterns: typed payload errors, extensions, or the project's existing GraphQL error policy.
- Paginate lists with the project's chosen style: cursor connections or offset pagination.

## Resolvers

- Keep resolvers thin: authorize, validate/coerce, call service/use-case/data layer, map result.
- Do not put large business workflows directly in field resolvers.
- Prevent N+1 queries with DataLoader, batching, preloading, joins, or the framework's equivalent.
- Keep database access out of frontend GraphQL documents and client code.

## Security

- Authorization is required in resolvers or the service layer, not only in frontend operation visibility.
- Limit query complexity, depth, or cost for public or multi-tenant APIs.
- Validate custom scalars and uploaded files.
- Disable or restrict introspection in production when the project's security posture requires it.
- Do not expose secret, private, internal, or cross-tenant fields.

## Client Usage

- Keep GraphQL documents near features or in the project's established operation folder.
- Prefer generated types when the project supports them.
- Avoid duplicating fragments for the same UI concept.
- Keep cache update rules explicit.

## Review Smells

- resolver directly mirrors database table access without authorization;
- N+1 query risk in nested fields;
- mutation returns only `Boolean` with no error detail;
- generic JSON arguments where typed inputs would work;
- unbounded list fields;
- frontend operation requests sensitive fields it does not render;
- generated GraphQL types are stale.
