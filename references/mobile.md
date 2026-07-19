# Mobile Standards

Use for React Native, Flutter, Swift/iOS, Kotlin/Android, or hybrid mobile apps.

- Follow platform navigation, permissions, storage, background execution, and release conventions.
- Handle offline, poor network, retries, app resume, and version upgrades.
- Keep secrets out of mobile bundles; assume clients are inspectable.
- Validate permissions and privacy prompts against actual data use.
- Test critical flows on representative devices or simulators.

Review smells: business rules only enforced client-side, unsafe local token storage, missing offline/error states, excessive app startup work, release steps hidden in one person's machine.
