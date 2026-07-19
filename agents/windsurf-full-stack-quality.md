# Full-Stack Quality Rules

1. Use these rules for database, backend, frontend, HTTP API, GraphQL, security, testing, performance, observability, delivery/configuration, and utility/library work.
2. Review/audit mode is read-only. Do not edit files unless the user explicitly asks for implementation or document generation.
3. Inspect existing project conventions before recommending changes.
4. Prefer the smallest idiomatic change that improves correctness, maintainability, security, or consistency.
5. Every review finding must include evidence, impact, recommendation, and validation.
6. Use Markdown for human reports and JSON for structured findings.
7. Preserve the project's existing stack, framework, and style unless the user explicitly asks to change them.
8. For Vue, keep heavy JS/TS logic in composables, stores, services, or utilities.
9. For React, use hooks for reusable stateful behavior and utilities for pure logic.
10. For Angular, keep business/data logic in services or facades rather than components.
