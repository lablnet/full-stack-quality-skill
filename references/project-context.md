# Project Context, Memory, Drift, And CI Gates

Use this reference when the user wants more than a one-time review: project docs, long-term memory, target architecture, drift detection, health score, or CI review gates.

## What This Mode Adds

This mode turns review findings into a maintained project context:

1. Audit repo.
2. Decide target architecture.
3. Generate project docs.
4. Track long-term memory.
5. Verify drift.
6. Compute health score and trend.
7. Support CI quality gates.

## Long-Term Project Memory

Long-term project memory means durable files that future agents and developers read before changing code. It prevents the same architectural questions from being re-litigated every week.

Recommended files:

- `docs/agents.md`: short entry point for future AI agents.
- `docs/architecture.md`: target architecture and boundaries.
- `docs/decisions.md`: accepted ADRs.
- `docs/security.md`: security rules and known risks.
- `docs/testing.md`: testing expectations and critical paths.
- `docs/migration-backlog.md`: planned cleanup from current state to target state.
- `docs/audit/inventory.json`: health score, trend, counters, and run metadata.
- `docs/audit/drift-report.md`: doc-vs-code verification.
- `docs/audit/findings/*.findings.json`: per-area structured findings.

Keep memory concise. It should guide work, not become a second codebase.

## Health Score And Trend

A health score is a rough quality/risk indicator for comparing audit runs over time. It is not an objective truth. Its value comes from using the same formula consistently.

Default formula:

```text
raw = 100
  - 25 * critical_findings
  - 5 * high_findings
  - 2 * medium_findings
  - 0.5 * low_findings
  - 10 * untested_critical_paths
  - 10 * drift_mismatches
  + 0.2 * target_structure_pct

health_score = clamp(raw, 0, 100)
```

Track:

- current score;
- raw score;
- previous score;
- score delta;
- formula used;
- finding counts by severity;
- untested critical paths;
- drift mismatches;
- target architecture compliance.

## Drift Detection

Verify generated docs against current code and record mismatches in `docs/audit/drift-report.md`.

## Target Architecture Decisions

When the current project is inconsistent, propose 2-3 target architectures. Pick options that fit the actual stack and product:

- layered architecture;
- feature-sliced frontend;
- modular monolith;
- clean/hexagonal architecture;
- MVC/MVVM where appropriate;
- service-oriented only when the repo already needs that scale.

Each option should include:

- why it fits;
- target folder sketch;
- migration cost: S/M/L;
- risks;
- what future code should do immediately.

Accepted decisions go into `docs/decisions.md` as ADRs.

## Docs That Guide Future Agents

The generated docs should answer: "Before I edit this repo, what must I know?"

Good agent docs include:

- what architecture is target;
- where to put new code;
- what not to touch;
- how to validate changes;
- required tests;
- security rules;
- API conventions;
- UI conventions;
- known legacy exceptions;
- links to decisions and backlog.

Prefer short docs with links over huge duplicated documents.

## CI Quality Gate

A CI quality gate checks whether a PR/diff violates the project context.

It can be advisory or blocking.

Check:

- architecture boundaries;
- security rules;
- database migration safety;
- required tests for touched areas;
- API/GraphQL contract consistency;
- frontend design-system rules;
- no new undocumented dependency or framework;
- docs updated when architecture/security/API behavior changes.

Suggested CI result:

- pass: no blocking issues;
- warn: non-blocking drift or missing docs;
- fail: critical/high security, auth, data, migration, or architecture violation.
