# Frontend Example: Angular

Use this shape for Angular projects. Components should handle presentation and user interaction; services should own data and business workflows.

## Component

```ts
@Component({
  selector: "app-order-create",
  templateUrl: "./order-create.component.html"
})
export class OrderCreateComponent {
  readonly form = this.orderForm.create();
  readonly isSaving = signal(false);

  constructor(private readonly orders: OrderService, private readonly orderForm: OrderFormService) {}

  save(): void {
    if (this.form.invalid) return;
    this.orders.create(this.form.getRawValue());
  }
}
```

## Service

```ts
@Injectable({ providedIn: "root" })
export class OrderService {
  constructor(private readonly http: HttpClient) {}

  create(input: CreateOrderInput): Observable<Order> {
    return this.http.post<Order>("/api/orders", input);
  }
}
```

Avoid putting API orchestration, authorization rules, or complex transformations directly in the component.
