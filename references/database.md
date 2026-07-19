# Database Standards

Use these standards for relational databases, document databases, and ORM-backed schemas. Apply them through the project's existing database technology.

## Schema Source

- Identify the source of truth: migrations, ORM models, schema files, or managed database definitions.
- Do not let migrations, models, and raw SQL disagree. If they do, report a `schema-source-conflict`.
- Schema changes require migration files, rollback or forward-fix strategy, and test data considerations.

## Normalization

- Start with 3NF for transactional data: one fact in one place, stable foreign keys, no repeated groups.
- Use join tables for many-to-many relationships.
- Keep computed or duplicated fields only when they are derived, documented, and refreshed consistently.
- Denormalize only for clear read-performance, analytics, or integration reasons; name the owner of the duplicated value.

## Keys And Names

- Primary keys: use one consistent strategy per domain area, such as `id`, `user_id`, or UUID identifiers.
- Foreign keys should name the referenced entity: `user_id`, `order_id`, `tenant_id`.
- Boolean names should read naturally: `is_active`, `has_paid`, `can_export`.
- Timestamps should be explicit: `created_at`, `updated_at`, `deleted_at`, `published_at`.
- Avoid vague fields: `data`, `value`, `type`, `status` without constraints or enums.

## Integrity

- Required values should be `NOT NULL` unless the domain truly allows absence.
- Use unique constraints for business uniqueness, not only application checks.
- Add foreign keys when supported and appropriate.
- Use check constraints or enums for bounded states.
- Add indexes for foreign keys, lookup fields, and frequent filters/sorts. Avoid unused indexes on hot write tables.

## Data Access

- Keep data access out of UI components and transport controllers.
- Prefer one data access style per project area: ORM, query builder, or SQL module.
- Raw SQL is fine when it is clearer or faster, but parameterize it and keep it near the data layer.
- Transactions belong around complete business operations, not individual statements.

## Review Smells

- nullable fields the code treats as always present;
- duplicated entity fields without sync rules;
- missing uniqueness for email, slug, external IDs, or tenant-scoped names;
- N+1 queries in list endpoints or UI loaders;
- migrations edited after release;
- soft delete without filtered uniqueness or restore rules.
