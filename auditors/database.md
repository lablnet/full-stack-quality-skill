# Database Auditor

Use with `references/database.md`.

Inspect:

1. Schema source of truth: migrations, ORM models, raw SQL, schema dumps.
2. Normalization: repeated fields, JSON blobs hiding relational data, many-to-many design.
3. Key names: primary keys, foreign keys, tenant keys, timestamps.
4. Constraints: `NOT NULL`, unique, foreign keys, checks/enums.
5. Indexes: frequent filters, joins, sorting, foreign keys, unused indexes.
6. Migrations: order, rollback/forward-fix safety, edited historical migrations.
7. Access patterns: ORM/raw SQL/query builder consistency, N+1 risk, transactions.

Typical findings:

- `schema-source-conflict`
- `normalization-risk`
- `inconsistent-key-naming`
- `missing-constraint`
- `missing-index`
- `unsafe-migration`
- `query-in-wrong-layer`
