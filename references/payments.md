# Payments And Billing Standards

Use for payments, subscriptions, invoices, refunds, credits, taxes, webhooks, and billing portals.

- Payment and billing mutations must be idempotent.
- Verify webhook signatures and handle duplicate/out-of-order events.
- Reconcile local state against the payment provider.
- Store only safe payment metadata; never store raw card data unless the system is explicitly compliant.
- Refunds, cancellations, trials, proration, and invoice states need clear state transitions.

Review smells: webhook not verified, payment retry creates duplicate order, no reconciliation, invoice state inferred from UI only, missing audit trail.
