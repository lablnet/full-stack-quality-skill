# Email And Notification Standards

Use for email, SMS, push, in-app notifications, webhooks to users, and transactional messaging.

- Templates should be versioned or traceable.
- Delivery should be retryable and observable.
- Unsubscribe, consent, and notification preferences must be respected.
- Avoid secrets, tokens, or excessive PII in notification content.
- Critical notifications should be idempotent or deduplicated.

Review smells: no unsubscribe path, notification sent inside DB transaction unsafely, duplicate sends on retry, PII in subject line, no delivery/failure tracking.
