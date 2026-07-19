# Delivery And Configuration Standards

Use these standards for CI/CD, environments, deployment, runtime configuration, and operational safety.

## Configuration

- Configuration should be explicit per environment.
- Secrets must not be committed.
- Defaults should be safe for local development, not accidentally production-like.
- Feature flags should have owners and cleanup plans.

## CI/CD

- CI should run the checks the project relies on: formatting, linting, type checks, tests, security/dependency audits, migrations when available.
- Keep CI deterministic and reasonably fast.
- Block deployment on critical security, failing tests, broken migrations, or type errors when the project supports those checks.

## Deployment Safety

- Database migrations should be compatible with rolling deploys when the system deploys that way.
- Separate schema changes from code changes when needed.
- Have rollback or forward-fix strategy for risky deploys.
- Background workers, queues, cron jobs, and scheduled tasks need deploy/update consideration.

## Review Smells

- production secrets in repo config;
- CI does not run tests or type checks;
- migrations require downtime without being called out;
- feature flag with no removal plan;
- deployment depends on manual hidden steps;
- environment names or config keys differ randomly across services.
