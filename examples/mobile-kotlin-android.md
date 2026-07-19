# Mobile Example: Kotlin / Android

Use this for native Android apps. Keep UI state in ViewModels and platform/data behavior in repositories/services.

```kotlin
class OrdersViewModel(
    private val orders: OrderRepository
) : ViewModel() {
    val state = orders.observeOrders()
        .map { OrdersState(items = it) }
        .stateIn(viewModelScope, SharingStarted.WhileSubscribed(), OrdersState())
}
```

Check permissions, lifecycle, offline state, secure storage, release variants, and background work constraints.
