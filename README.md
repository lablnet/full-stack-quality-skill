# Full-Stack Quality Skill

A reusable AI coding skill for reviewing, designing, and implementing maintainable full-stack software.

It covers database design, backend architecture, frontend architecture, HTTP APIs, GraphQL, security, utilities, testing, performance, observability, and delivery/configuration.

## What This Skill Is For

- Read-only code reviews and audits.
- Full-stack implementation guidance.
- Architecture and ADR support.
- Database normalization and migration review.
- API design review for REST/HTTP and GraphQL.
- Frontend framework guidance for React, Vue, Angular, Svelte, and server-rendered templates.
- Security, testing, performance, observability, and CI/CD hygiene.

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

## Install

Clone the repository:

```sh
git clone https://github.com/lablnet/full-stack-quality-skill.git
cd full-stack-quality-skill
```

Repository URL:

```text
https://github.com/lablnet/full-stack-quality-skill.git
```

## Install For Codex / OpenAI-Style Agents

For a project-level instruction file, copy the adapter to the target project root:

```sh
cp agents/codex-AGENTS.md /path/to/your-project/AGENTS.md
```

Then copy or install the skill folder wherever your Codex environment loads skills from. If your environment supports workspace skills, place the full `full-stack-quality-skill` folder in that skill location.

Use it with prompts like:

```text
Use full-stack-quality to review this project. Audit only, read-only.
```

```text
Use full-stack-quality to review the backend, database schema, and HTTP API. Produce review.md and findings.json.
```

## Install For Claude Code

Copy the Claude adapter to the target project root:

```sh
cp agents/claude-CLAUDE.md /path/to/your-project/CLAUDE.md
```

If the project already has `CLAUDE.md`, merge the relevant rules instead of overwriting it.

Use it with prompts like:

```text
Use the full-stack-quality rules to audit this repo. Do not edit files.
```

## Install For Cursor

Create the Cursor rules directory and copy the rule:

```sh
mkdir -p /path/to/your-project/.cursor/rules
cp agents/cursor-full-stack-quality.mdc /path/to/your-project/.cursor/rules/full-stack-quality.mdc
```

Use it in Cursor by asking:

```text
Apply the full-stack-quality rule and review the frontend architecture.
```

## Install For Antigravity

Antigravity supports workspace rules under `.agents/rules/` and workspace skills under `.agents/skills/`.

For a workspace rule:

```sh
mkdir -p /path/to/your-project/.agents/rules
cp agents/antigravity-full-stack-quality.md /path/to/your-project/.agents/rules/full-stack-quality.md
```

For a workspace skill:

```sh
mkdir -p /path/to/your-project/.agents/skills
cp -R . /path/to/your-project/.agents/skills/full-stack-quality
```

Use it with:

```text
Use the full-stack-quality skill to review this project read-only.
```

## Install For Gemini Tools That Support AGENTS.md

Copy the Gemini adapter to the project root:

```sh
cp agents/gemini-AGENTS.md /path/to/your-project/AGENTS.md
```

Use it with:

```text
Use the AGENTS.md full-stack quality rules to audit this codebase.
```

## Install For Windsurf

For modern Windsurf rules, copy the starter rule to the project rules directory:

```sh
mkdir -p /path/to/your-project/.windsurf/rules
cp agents/windsurf-full-stack-quality.md /path/to/your-project/.windsurf/rules/full-stack-quality.md
```

If your setup uses the legacy root `.windsurfrules` file, merge the contents of `agents/windsurf-full-stack-quality.md` into `.windsurfrules`.

Use it with:

```text
Review this repo using the full-stack-quality rules. Audit only.
```

## Output Formats

- Markdown for human review reports, explanations, ADRs, and implementation plans.
- JSON for structured findings and machine-readable checklists.
- YAML only when the existing project/tool requires YAML or the user asks for it.

Preferred audit output:

```text
findings.json
review.md
```

For larger audits, multiple JSON files are fine:

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

Use one `findings.json` for small reviews. Use per-area JSON files when the review is large or when separate tools/agents will process each area.

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
