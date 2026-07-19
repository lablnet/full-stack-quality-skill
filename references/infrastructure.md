# Infrastructure Standards

Use for Docker, Terraform, Kubernetes, cloud resources, IAM, networking, storage, and runtime platforms.

- Prefer declarative infrastructure committed to version control.
- Use least-privilege IAM and narrow network exposure.
- Keep secrets in secret managers, not images or repo files.
- Keep environment parity for critical services.
- Make backups, retention, scaling, and rollback behavior explicit.

Review smells: public database/storage, wildcard IAM, manual console-only resources, secrets in Docker images, no backups, environment drift.
