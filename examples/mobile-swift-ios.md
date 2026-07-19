# Mobile Example: Swift / iOS

Use this for native iOS apps. Keep views focused on presentation and place state/data behavior in view models, services, or repositories according to the project style.

```swift
@MainActor
final class OrdersViewModel: ObservableObject {
    @Published private(set) var orders: [Order] = []
    private let service: OrderService

    init(service: OrderService) {
        self.service = service
    }

    func load() async throws {
        orders = try await service.fetchOrders()
    }
}
```

Check permissions, keychain/storage, offline behavior, app lifecycle, and release configuration.
