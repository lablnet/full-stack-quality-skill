# Mobile Example: Flutter

Use this for Flutter apps. Keep widgets focused on UI and move business/data behavior into services, controllers, blocs, notifiers, or repositories according to the project style.

```dart
class OrdersPage extends StatelessWidget {
  const OrdersPage({super.key});

  @override
  Widget build(BuildContext context) {
    final orders = context.watch<OrderController>();

    return Scaffold(
      appBar: AppBar(title: const Text("Orders")),
      body: OrderList(orders: orders.items),
    );
  }
}
```

Check permissions, offline states, secure storage, app lifecycle, and release configuration.
