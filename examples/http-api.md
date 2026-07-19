# HTTP API Examples

## Resource Endpoints

```http
GET /orders?status=paid&page=1
POST /orders
GET /orders/{order_id}
PATCH /orders/{order_id}
DELETE /orders/{order_id}
```

## Create Response

```http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "id": "ord_123",
  "status": "draft",
  "total": 4500
}
```

## Validation Error

```json
{
  "error": {
    "code": "validation_failed",
    "message": "One or more fields are invalid.",
    "fields": {
      "items": "At least one item is required."
    }
  }
}
```
