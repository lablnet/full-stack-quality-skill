# Mobile Example: React Native

Use this for React Native apps. Components compose UI; hooks/services own reusable state and data behavior.

```tsx
export function OrdersScreen() {
  const orders = useOrders();

  return (
    <Screen>
      <Header title="Orders" />
      <OrderList orders={orders.data} refreshing={orders.isLoading} />
    </Screen>
  );
}
```

Review native permissions, offline behavior, secure storage, navigation, and app lifecycle.
