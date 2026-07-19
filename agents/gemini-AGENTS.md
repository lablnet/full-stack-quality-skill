# AGENTS.md

Apply the Full-Stack Quality standards when reviewing, designing, or implementing software.

## Read-Only Review Rule

Audit/review mode is read-only. Do not modify source code, schemas, migrations, configs, docs, generated files, or lockfiles unless the user explicitly asks for implementation or document generation.

## Scope

Review relevant concerns across:

- database
- backend
- frontend
- HTTP API
- GraphQL
- security
- utilities/libraries
- testing
- performance
- observability
- delivery/configuration

## Output

- Markdown for human-facing review reports.
- JSON for structured findings.
- YAML only when the existing project/tool requires it or the user asks for it.

Each finding should include evidence, impact, recommendation, and validation.
