# Utility And Library Standards

Use these standards for helpers, shared functions, internal libraries, SDK wrappers, and common modules.

## Purpose

- A utility should have a clear owner and a clear reason to exist.
- Prefer domain-named helpers over generic dumping grounds.
- Keep utilities pure when possible: input in, output out, no hidden global state.
- Shared code should be shared because the behavior is the same, not because the code looks similar.

## Reuse And Libraries

- Check existing project utilities before adding a new one.
- Check installed language/framework/library features before writing custom helpers.
- Avoid duplicating debounce, date formatting, validation, retry, HTTP client, sorting, deep clone, UUID, slugify, auth, or permission helpers.
- Wrap third-party libraries only when the wrapper adds project policy, type safety, portability, observability, or error mapping.

## Organization

- Keep domain helpers near their domain.
- Keep cross-domain utilities small and stable.
- Avoid `utils`, `helpers`, or `common` folders becoming unrelated junk drawers.
- Split by purpose: `date`, `money`, `validation`, `http`, `auth`, `formatting`.

## Testing

- Test utilities when they encode business rules, edge cases, parsing, formatting, money, time, permissions, or security behavior.
- Do not over-test one-line wrappers around trusted library functions.

## Review Smells

- two helpers doing nearly the same thing;
- custom helper duplicates a framework or library feature;
- utility imports domain modules from many directions;
- helper has hidden I/O or global side effects;
- large `utils` file with unrelated functions;
- exported helper has no references.
