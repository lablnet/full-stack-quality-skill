# Backend Example: PHP / Laravel

Use Laravel conventions when the project is Laravel. Do not add extra layers when models, policies, requests, and actions are enough.

## Controller

```php
public function store(StoreOrderRequest $request): JsonResponse
{
    $order = $this->createOrder->handle($request->validated(), $request->user());

    return response()->json($order, 201);
}
```

## Action

```php
final class CreateOrder
{
    public function handle(array $data, User $user): Order
    {
        return DB::transaction(function () use ($data, $user) {
            return Order::create([
                'user_id' => $user->id,
                'total' => OrderTotal::fromItems($data['items']),
                'status' => OrderStatus::Draft,
            ]);
        });
    }
}
```
