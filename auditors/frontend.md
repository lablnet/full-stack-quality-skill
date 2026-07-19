# Frontend Auditor

Use with `references/frontend.md`.

Inspect:

1. Component inventory: shared UI, feature components, pages/routes.
2. Duplicates: Button, Modal, Input, Table, Toast, Card, Form, Badge.
3. Styling: tokens, CSS variables, utility classes, inline styles, hardcoded values.
4. State: server state, form state, local UI state, global state.
5. Framework logic placement:
   - Vue: pages/components should not contain large JavaScript/TypeScript logic; prefer composables, stores, services, and utilities.
   - React: reusable stateful logic should be hooks; pure logic should be utilities.
   - Angular: business/data logic should live in services, not components.
6. API boundaries: low-level components calling APIs directly.
7. Accessibility: semantic controls, labels, focus, keyboard use, contrast.
8. Responsive layout: overlap, text fitting, layout shift, mobile behavior.

Typical findings:

- `duplicate-component`
- `hardcoded-design-value`
- `mixed-styling-approaches`
- `api-call-in-presentational-component`
- `logic-in-page-component`
- `missing-composable-or-hook`
- `inaccessible-control`
- `responsive-layout-risk`
