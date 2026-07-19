# Frontend Web Standards

Use these standards for React, Vue, Svelte, Angular, server-rendered templates, or any web frontend.

## Structure

- Follow the existing route/page/component organization.
- Keep page components focused on composition and data flow.
- Move reusable UI to shared components only when reuse is real and the API is stable.
- Keep domain-specific components near the feature they serve.
- Separate state ownership: local UI state, server/cache state, form state, and global app state should not blur together.
- Keep heavy logic out of page and presentational component files. Use the framework's standard logic unit: Vue composables, React hooks, Angular services/facades, Svelte stores/modules, or plain utilities.

## Framework-Specific Logic Placement

- Vue: page and component `.vue` files should mostly compose template, props, emits, and small wiring. Put reusable JavaScript/TypeScript logic in `composables`, feature services, stores, or utilities.
- React: components should render UI and wire events. Put reusable stateful behavior in hooks, server/cache behavior in the project data layer, and pure logic in utilities.
- Angular: components should stay presentation-oriented. Put business/data logic in services, shared reactive state in services/stores, and reusable transformations in pipes or utilities.
- Svelte: components should stay focused on markup and interaction. Put shared state in stores and reusable logic in modules.
- Server-rendered templates: keep templates free of business logic; move behavior into controllers/view models/helpers according to the framework.

## UI Consistency

- Reuse the project's design system, component library, tokens, spacing scale, colors, typography, and interaction patterns.
- Avoid duplicate Button, Modal, Input, Table, Toast, Badge, Card, and Form components unless there is a deliberate reason.
- Prefer tokens or CSS variables over hardcoded colors and spacing.
- Keep visual hierarchy proportional to context: dashboards and tools should be scan-friendly; marketing pages can be more expressive.

## Accessibility

- Use semantic HTML before ARIA.
- Form controls need labels, validation messages, keyboard access, and focus states.
- Interactive elements must be buttons or links as appropriate.
- Maintain color contrast and visible focus.
- Do not rely on color alone for status.

## Responsive Behavior

- Define stable layout constraints for fixed-format controls, tables, cards, boards, and toolbars.
- Text must fit on mobile and desktop without overlapping other UI.
- Use responsive grids and wrapping toolbars; avoid viewport-scaled font sizes.

## Data And Effects

- Keep API calls centralized through the existing client/loaders/actions pattern.
- Handle loading, empty, error, success, disabled, and optimistic states where relevant.
- Cancel or ignore stale async results when components unmount or inputs change.
- Keep derived state derived; do not duplicate server data in local state unnecessarily.

## Review Smells

- multiple visually different controls for the same action type;
- hardcoded colors, spacing, shadows, radii, or fonts scattered through views;
- API calls hidden inside low-level presentational components;
- Vue page/component files containing large business logic instead of composables/services;
- React components containing reusable state machines or business rules instead of hooks/utilities;
- Angular components directly owning data access or business workflows instead of services;
- form validation only on submit or only on the client;
- inaccessible clickable divs;
- layout shifts when labels, counts, or loading text change.
