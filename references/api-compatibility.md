# API Compatibility And Versioning Standards

Use for public APIs, mobile clients, integrations, SDKs, GraphQL contracts, and long-lived frontend/backend contracts.

- Avoid breaking changes without versioning, migration path, or deprecation window.
- Treat response field removal, type changes, enum changes, and error-shape changes as compatibility risks.
- Additive changes are usually safer, but still consider old clients.
- Document deprecations and sunset dates.
- Contract tests are valuable for critical clients.

Review smells: renamed JSON field without compatibility layer, enum value removed, GraphQL field nullability tightened, mobile API changed without versioning, no deprecation plan.
