# Frontend Example: React

Use this shape for React projects, adapting to the existing data fetching and component conventions.

## Feature Component

```tsx
export function OrderCreateForm() {
  const createOrder = useCreateOrder();

  return (
    <Form onSubmit={createOrder.submit}>
      <TextField name="customerEmail" label="Customer email" required />
      <OrderItemsField name="items" />
      <Button type="submit" disabled={createOrder.isPending}>
        Save
      </Button>
    </Form>
  );
}
```

## UI Rule

Use the canonical design-system component:

```tsx
<Button variant="primary" size="sm">Save</Button>
```

Avoid one-off inline styling:

```tsx
<button style={{ background: "#2563eb", padding: 12 }}>Save</button>
```
