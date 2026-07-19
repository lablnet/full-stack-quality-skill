# Backend Example: Django

Use Django conventions first. Keep views thin and place reusable business workflows in services or model managers when needed.

## View

```py
@require_POST
def create_order(request):
    payload = CreateOrderForm(request.POST)
    if not payload.is_valid():
        return JsonResponse({"errors": payload.errors}, status=422)

    order = order_service.create_order(payload.cleaned_data, request.user)
    return JsonResponse(OrderSerializer(order).data, status=201)
```

## Service

```py
@transaction.atomic
def create_order(data: dict, user: User) -> Order:
    total = calculate_order_total(data["items"])
    return Order.objects.create(user=user, total=total, status=Order.Status.DRAFT)
```
