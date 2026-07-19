# CLAUDE.md

Use this project instruction as the Claude Code adapter for the `full-stack-quality` skill.

## Full-Stack Quality

When reviewing, designing, or implementing full-stack software, apply the standards from the skill's `SKILL.md`, `references/`, `auditors/`, `examples/`, and `templates/` folders.

## Review Mode

- Reviews and audits are read-only.
- Do not modify source code, schema files, migrations, configs, docs, generated files, or lockfiles unless the user explicitly asks for implementation or document generation.
- Findings must include evidence: path, line or symbol when available, observed behavior, impact, recommendation, and validation.
- Report findings first, ordered by severity.

## Output

- Use Markdown for human-facing reports, ADRs, and implementation plans.
- Use JSON for structured findings.
- Use YAML only if the project/tool already requires YAML or the user asks for it.

## Standards

Check database, backend, frontend, HTTP API, GraphQL, security, utilities, testing, performance, observability, and delivery/configuration concerns when relevant.
