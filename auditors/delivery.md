# Delivery And Configuration Auditor

Use with `references/delivery.md`.

Inspect:

1. Environment config files and secret handling.
2. CI workflows and required checks.
3. Build, lint, typecheck, test, audit, migration commands.
4. Deployment scripts and hidden manual steps.
5. Database migration safety for the deployment style.
6. Feature flags and stale environment toggles.
7. Worker, queue, cron, and scheduled task deploy behavior.

Typical findings:

- `secret-in-config`
- `missing-ci-check`
- `unsafe-deploy-migration`
- `manual-deploy-step`
- `stale-feature-flag`
- `environment-config-drift`
