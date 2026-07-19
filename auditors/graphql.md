# GraphQL Auditor

Use with `references/graphql.md`.

Run this auditor only when the project has GraphQL schema files, resolver files, GraphQL client operations, or GraphQL dependencies.

Inspect:

1. Schema design: types, inputs, enums, nullability, naming, database leakage.
2. Query/mutation semantics and return payloads.
3. Resolver boundaries: thin resolvers, business logic placement, data access placement.
4. Authorization in resolvers or service layer.
5. N+1 prevention: DataLoader, batching, preloading, joins.
6. Pagination, filtering, sorting, and unbounded list fields.
7. Query complexity/depth/cost controls when relevant.
8. Client operations: generated types, fragment duplication, sensitive over-fetching.

Typical findings:

- `graphql-schema-leaks-database`
- `graphql-nullability-risk`
- `graphql-thick-resolver`
- `graphql-missing-authz`
- `graphql-n-plus-one`
- `graphql-unbounded-list`
- `graphql-overfetching`
- `graphql-stale-generated-types`
