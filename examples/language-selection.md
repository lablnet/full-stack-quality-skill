# Language And Framework Selection

Use exact examples when available. If the exact language or framework is not represented, translate the closest architectural pattern into the project's existing style.

Rules:

- Do not force an example's framework onto a project.
- Prefer the repo's existing conventions over the example.
- Use backend examples for layer shape: route/controller -> service/use-case -> repository/data access.
- Use frontend examples for logic placement: components compose UI; hooks/composables/services/modules hold reusable logic.
- Use mobile examples for platform concerns: permissions, offline behavior, storage, navigation, release safety.
- Use SQL/HTTP/GraphQL examples for contract shape, not exact naming.
