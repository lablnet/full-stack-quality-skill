# Backend Example: C# / ASP.NET Core

Use this shape for ASP.NET Core APIs. Keep controllers thin and put business behavior in services.

## Controller

```csharp
[ApiController]
[Route("api/orders")]
public sealed class OrdersController : ControllerBase
{
    private readonly OrderService orders;

    public OrdersController(OrderService orders)
    {
        this.orders = orders;
    }

    [HttpPost]
    public async Task<ActionResult<OrderDto>> Create(CreateOrderRequest request)
    {
        var order = await orders.CreateOrderAsync(request, User);
        return CreatedAtAction(nameof(Get), new { id = order.Id }, order);
    }
}
```

## Service

```csharp
public sealed class OrderService
{
    private readonly IOrderRepository orders;

    public OrderService(IOrderRepository orders)
    {
        this.orders = orders;
    }

    public Task<OrderDto> CreateOrderAsync(CreateOrderRequest request, ClaimsPrincipal user)
    {
        var total = OrderTotals.FromItems(request.Items);
        return orders.CreateAsync(request, user.GetUserId(), total);
    }
}
```
