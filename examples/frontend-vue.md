# Frontend Example: Vue

Use this shape for Vue projects, adapting to the existing store, composable, and component conventions.

```vue
<script setup lang="ts">
const form = useOrderForm();
const createOrder = useCreateOrder();
</script>

<template>
  <form @submit.prevent="createOrder.submit(form.value)">
    <TextField v-model="form.customerEmail" label="Customer email" required />
    <OrderItemsField v-model="form.items" />
    <Button type="submit" :disabled="createOrder.isPending">Save</Button>
  </form>
</template>
```

Keep presentational components free of direct API calls unless the existing framework pattern says otherwise.
