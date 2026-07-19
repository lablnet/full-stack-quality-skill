# Frontend Example: SvelteKit

Use this for SvelteKit projects. Keep load functions, actions, stores, and components in their proper roles.

## Load Function

```ts
export async function load({ fetch }) {
  const response = await fetch("/api/orders");
  return {
    orders: await response.json()
  };
}
```

## Component

```svelte
<script lang="ts">
  export let data;
</script>

<PageHeader title="Orders" />
<OrderTable orders={data.orders} />
```

Put shared state in stores and reusable logic in modules.
