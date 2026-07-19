# Backend Example: Go

Use this shape for Go services. Keep handlers thin, dependencies explicit, and business logic testable.

## Handler

```go
func (h *OrderHandler) Create(w http.ResponseWriter, r *http.Request) {
	var input CreateOrderRequest
	if err := json.NewDecoder(r.Body).Decode(&input); err != nil {
		writeError(w, http.StatusBadRequest, err)
		return
	}

	order, err := h.orders.Create(r.Context(), input, userIDFrom(r))
	if err != nil {
		writeError(w, http.StatusUnprocessableEntity, err)
		return
	}

	writeJSON(w, http.StatusCreated, order)
}
```

## Service

```go
type OrderService struct {
	repo OrderRepository
}

func (s OrderService) Create(ctx context.Context, input CreateOrderRequest, userID string) (Order, error) {
	total := CalculateOrderTotal(input.Items)
	return s.repo.Create(ctx, NewOrder{
		UserID: userID,
		Items:  input.Items,
		Total:  total,
	})
}
```
