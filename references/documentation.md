# Documentation Quality Standards

Use for README, onboarding docs, API docs, generated project docs, architecture docs, and agent instructions.

- Docs should be concise, accurate, task-oriented, and linked to decisions.
- Avoid duplicating code facts that can be derived from source.
- Mark known legacy exceptions clearly.
- Update docs when architecture, API, schema, security, or setup changes.
- Verify docs against code when docs guide agents or CI gates.

Review smells: stale setup commands, undocumented env vars, architecture docs that no longer match code, missing API examples, huge docs nobody reads.
