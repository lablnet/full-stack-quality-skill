# Backend Example: Java / Spring

Use Spring conventions when the project is Spring. Keep controllers thin and services transactional where business operations require it.

## Controller

```java
@PostMapping("/orders")
public ResponseEntity<OrderResponse> create(@Valid @RequestBody CreateOrderRequest request) {
    OrderResponse order = orderService.createOrder(request);
    return ResponseEntity.status(HttpStatus.CREATED).body(order);
}
```

## Service

```java
@Service
public class OrderService {
    private final OrderRepository orders;

    public OrderService(OrderRepository orders) {
        this.orders = orders;
    }

    @Transactional
    public OrderResponse createOrder(CreateOrderRequest request) {
        Order order = Order.create(request.items());
        return OrderResponse.from(orders.save(order));
    }
}
```
