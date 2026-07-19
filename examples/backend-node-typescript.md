# Backend Example: Node.js / TypeScript

Use this shape for Express, Fastify, Nest-like services, or similar TypeScript backends. Adapt names to the repo.

## Thin Route

```ts
router.post("/orders", async (req, res, next) => {
  try {
    const input = createOrderSchema.parse(req.body);
    const order = await orderService.createOrder(input, req.user.id);
    res.status(201).json(order);
  } catch (error) {
    next(error);
  }
});
```

## Service

```ts
export class OrderService {
  constructor(private readonly orders: OrderRepository) {}

  async createOrder(input: CreateOrderInput, userId: string) {
    const total = calculateOrderTotal(input.items);
    return this.orders.create({ ...input, userId, total });
  }
}
```

## Repository

```ts
export class OrderRepository {
  async create(order: NewOrder) {
    return db.order.create({ data: order });
  }
}
```
