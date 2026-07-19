# Full-Stack Quality Skill

A reusable AI coding skill for reviewing, designing, and implementing maintainable full-stack software.

It covers database design, backend architecture, frontend architecture, mobile, HTTP APIs, GraphQL, security, privacy, accessibility, i18n, analytics, background jobs, AI/LLM safety, infrastructure, documentation, utilities, testing, performance, observability, and delivery/configuration.

## What This Skill Is For

- Read-only code reviews and audits.
- Full-stack implementation guidance.
- Architecture and ADR support.
- Database normalization and migration review.
- API design review for REST/HTTP and GraphQL.
- Frontend framework guidance for React, Vue, Angular, Svelte, and server-rendered templates.
- Security, testing, performance, observability, and CI/CD hygiene.
- Optional project context mode: audit repo, decide target architecture, generate project docs, verify drift, track long-term memory, health score, and CI quality gates.

## Core Rule

Audit/review mode is read-only. The agent may recommend changes, but must not edit source code, schemas, configs, docs, generated files, or lockfiles unless the user explicitly asks for implementation or document generation.

## Folder Structure

```text
full-stack-quality/
├── SKILL.md
├── README.md
├── agents/
│   ├── openai.yaml
│   ├── codex-AGENTS.md
│   ├── claude-CLAUDE.md
│   ├── cursor-full-stack-quality.mdc
│   ├── antigravity-full-stack-quality.md
│   ├── gemini-AGENTS.md
│   └── windsurf-full-stack-quality.md
├── auditors/
├── examples/
├── references/
└── templates/
```

## Installation

### Codex / OpenAI-Style Agents

Codex-style agents can use the skill through `AGENTS.md`:

```sh
git submodule add https://github.com/lablnet/full-stack-quality-skill.git tools/full-stack-quality
```

Add this to the project's `AGENTS.md`:

```text
For full-stack quality reviews, read tools/full-stack-quality/SKILL.md
and follow it. Supporting files are in the same folder.
```

Use it with prompts like:

```text
Use full-stack-quality to review this project. Audit only, read-only.
```

```text
Use full-stack-quality to review the backend, database schema, and HTTP API. Produce review.md and findings.json.
```

### Claude Code

For all projects, install the skill in your personal Claude skills directory:

```sh
git clone https://github.com/lablnet/full-stack-quality-skill.git ~/.claude/skills/full-stack-quality
```

For one project, add it inside the repository:

```sh
git submodule add https://github.com/lablnet/full-stack-quality-skill.git .claude/skills/full-stack-quality
```

If the project needs persistent Claude instructions, copy or merge:

```sh
cp .claude/skills/full-stack-quality/agents/claude-CLAUDE.md CLAUDE.md
```

Use it with prompts like:

```text
Use the full-stack-quality rules to audit this repo. Do not edit files.
```

### Cursor

Install the skill inside Cursor's project tools folder:

```sh
git submodule add https://github.com/lablnet/full-stack-quality-skill.git .cursor/tools/full-stack-quality
```

Create `.cursor/rules/full-stack-quality.mdc`:

```text
---
description: Full-stack quality review for database, backend, frontend, APIs, GraphQL, security, testing, performance, observability, delivery, and utilities.
---

Read .cursor/tools/full-stack-quality/SKILL.md and follow it.
```

Use it with:

```text
Apply the full-stack-quality rule and review the frontend architecture.
```

### Antigravity

Antigravity supports workspace rules under `.agents/rules/` and workspace skills under `.agents/skills/`.

For a workspace skill:

```sh
git submodule add https://github.com/lablnet/full-stack-quality-skill.git .agents/skills/full-stack-quality
```

Optional workspace rule in `.agents/rules/full-stack-quality.md`:

```text
Read .agents/skills/full-stack-quality/SKILL.md and follow it for full-stack quality review and implementation tasks.
```

Use it with:

```text
Use the full-stack-quality skill to review this project read-only.
```

### Gemini Tools That Support AGENTS.md

Install the skill as a project tool:

```sh
git submodule add https://github.com/lablnet/full-stack-quality-skill.git tools/full-stack-quality
```

Add this to `AGENTS.md`:

```text
For full-stack quality reviews, read tools/full-stack-quality/SKILL.md
and follow it. Supporting files are in the same folder.
```

Use it with:

```text
Use the AGENTS.md full-stack quality rules to audit this codebase.
```

### Windsurf

Install the skill as a project tool:

```sh
git submodule add https://github.com/lablnet/full-stack-quality-skill.git tools/full-stack-quality
```

Create `.windsurf/rules/full-stack-quality.md`:

```text
Read tools/full-stack-quality/SKILL.md and follow it for full-stack quality review and implementation tasks.
```

If your setup uses the legacy root `.windsurfrules` file, add the same instruction there.

Use it with:

```text
Review this repo using the full-stack-quality rules. Audit only.
```

## Output Formats

- Markdown for human review reports, explanations, ADRs, and implementation plans.
- JSON for structured findings and machine-readable checklists.
- YAML only when the existing project/tool requires YAML or the user asks for it.

Preferred output for small or narrow audits:

```text
findings.json
review.md
```

Preferred output for broad or parallel audits:

```text
review.md
findings/
├── database.findings.json
├── backend.findings.json
├── frontend.findings.json
├── http-api.findings.json
├── graphql.findings.json
├── security.findings.json
├── utilities.findings.json
├── testing.findings.json
├── performance.findings.json
├── observability.findings.json
└── delivery.findings.json
```

Use one `findings.json` for small reviews. Use per-area JSON files by default when the review is broad, parallel, or when separate tools/agents will process each area.

## Project Context Mode

For deeper repository work, the skill can also:

- audit the repo;
- decide a target architecture;
- generate docs that guide future agents;
- keep long-term project memory;
- compute health score and trend;
- verify drift;
- support CI quality gates.

Recommended files:

```text
docs/
├── agents.md
├── architecture.md
├── decisions.md
├── security.md
├── testing.md
├── migration-backlog.md
└── audit/
    ├── inventory.json
    ├── drift-report.md
    └── findings/
        ├── backend.findings.json
        └── security.findings.json
```

## Agent Tool Adapters

The `agents/` folder contains copyable starter files for popular AI coding tools:

- Codex/OpenAI-style agents: copy `agents/codex-AGENTS.md` to `AGENTS.md`.
- Claude Code: copy `agents/claude-CLAUDE.md` to `CLAUDE.md`.
- Cursor: copy `agents/cursor-full-stack-quality.mdc` to `.cursor/rules/full-stack-quality.mdc`.
- Antigravity: copy `agents/antigravity-full-stack-quality.md` to `.agents/rules/full-stack-quality.md`.
- Gemini tools that support agent files: copy `agents/gemini-AGENTS.md` to `AGENTS.md`.
- Windsurf: copy `agents/windsurf-full-stack-quality.md` to `.windsurf/rules/full-stack-quality.md` or adapt it to the project's Windsurf rules format.

## Suggested GitHub Repo Names

- `full-stack-quality-skill`
- `agent-fullstack-quality`
- `fullstack-architecture-auditor`
- `full-stack-code-review-skill`
- `ai-fullstack-standards`
- `fullstack-engineering-standards`

Recommended: `full-stack-quality-skill`.
