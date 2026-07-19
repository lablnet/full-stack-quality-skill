# Backend Example: Python

Use this shape for FastAPI, Flask, Django service layers, or similar Python backends.

## Thin Endpoint

```py
@router.post("/orders", status_code=201)
def create_order(payload: CreateOrderRequest, user: User = Depends(require_user)):
    return order_service.create_order(payload, user.id)
```

## Service

```py
class OrderService:
    def __init__(self, orders: OrderRepository):
        self.orders = orders

    def create_order(self, payload: CreateOrderRequest, user_id: str) -> Order:
        total = calculate_order_total(payload.items)
        return self.orders.create(payload, user_id=user_id, total=total)
```

## Repository

```py
class OrderRepository:
    def create(self, payload: CreateOrderRequest, user_id: str, total: int) -> Order:
        order = Order(user_id=user_id, total=total, items=payload.items)
        db.session.add(order)
        db.session.commit()
        return order
```
