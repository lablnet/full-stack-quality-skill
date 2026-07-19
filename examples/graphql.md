# GraphQL Examples

Adapt these examples to the project's GraphQL framework and naming style.

## Schema

```graphql
type Order {
  id: ID!
  status: OrderStatus!
  total: Money!
  items: [OrderItem!]!
  createdAt: DateTime!
}

enum OrderStatus {
  DRAFT
  PAID
  CANCELLED
}

input CreateOrderInput {
  items: [CreateOrderItemInput!]!
}

type CreateOrderPayload {
  order: Order
  errors: [UserError!]!
}

type Mutation {
  createOrder(input: CreateOrderInput!): CreateOrderPayload!
}
```

## Thin Resolver

```ts
export const resolvers = {
  Mutation: {
    createOrder: async (_parent, args, context) => {
      context.auth.requireUser();
      return orderService.createOrder(args.input, context.user.id);
    }
  },
  Order: {
    items: (order, _args, context) => {
      return context.loaders.orderItemsByOrderId.load(order.id);
    }
  }
};
```

## Client Operation

```graphql
mutation CreateOrder($input: CreateOrderInput!) {
  createOrder(input: $input) {
    order {
      id
      status
      total {
        amount
        currency
      }
    }
    errors {
      field
      message
    }
  }
}
```
