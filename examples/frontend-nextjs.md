# Frontend Example: Next.js

Use this for Next.js projects. Respect whether the repo uses App Router, Pages Router, server actions, API routes, or a separate backend.

## Server Component Composition

```tsx
export default async function OrdersPage() {
  const orders = await getOrders();

  return (
    <main>
      <PageHeader title="Orders" />
      <OrderTable orders={orders} />
    </main>
  );
}
```

## Client Component For Interaction

```tsx
"use client";

export function OrderFilters() {
  const filters = useOrderFilters();
  return <Select value={filters.status} onChange={filters.setStatus} />;
}
```

Keep server data loading, client interaction, and API mutation boundaries clear.
