# Backend Example: Ruby on Rails

Use Rails conventions first. Do not add service layers for trivial CRUD, but extract workflows when controllers/models become crowded.

## Controller

```ruby
class OrdersController < ApplicationController
  def create
    order = CreateOrder.call(order_params, current_user)
    render json: order, status: :created
  end

  private

  def order_params
    params.require(:order).permit(items: [:product_id, :quantity])
  end
end
```

## Application Service

```ruby
class CreateOrder
  def self.call(attrs, user)
    Order.transaction do
      Order.create!(
        user: user,
        total_cents: OrderTotal.from_items(attrs[:items]),
        status: "draft"
      )
    end
  end
end
```
