# Common Auditor Rules

Apply these rules to every audit area.

1. Inspect the existing conventions before judging them.
2. Every finding needs evidence: path, line or symbol when available, observed behavior, and why it matters.
3. Audits are read-only. Do not modify source code, schema files, migrations, configs, docs, generated files, or lockfiles during review.
4. Do not invent missing systems. If there is no database, frontend, or API layer, say so and skip that area.
5. Prefer actionable findings over broad opinions.
6. Separate current-state facts from target-state recommendations.
7. Recommend the smallest fix that improves correctness, maintainability, or consistency.
8. Security, auth, database migrations, destructive operations, and external services are high-risk; flag them clearly.
9. Use the severity definitions in `references/quality-checklist.json`.

Return findings as Markdown for humans. When writing files, use JSON for structured findings unless the project or user requires YAML.
