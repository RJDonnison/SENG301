# Shotgun Surgery

A single responsibility is split across many different classes, so a single change requires modifying many files. See [Types](/smells/types.md).

### Refactoring

Use Move Method and Move Field to consolidate related code into a single class.

## Example

```python
class Order:
    def __init__(self):
        self.status = "pending"

    def confirm(self):
        self.status = "confirmed"

class Inventory:
    def reserve_items(self, order_id):
        ...

class EmailService:
    def send_confirmation(self, email):
        ...

class AuditLog:
    def log_order_confirmed(self, order_id):
        ...
```

(Every new order feature requires touching all four files.)

## Refactored

```python
class OrderService:
    def confirm_order(self, order_id):
        order = OrderRepository.find(order_id)
        order.confirm()
        Inventory.reserve_items(order_id)
        EmailService.send_confirmation(order.customer_email)
        AuditLog.log_order_confirmed(order_id)
        OrderRepository.save(order)
```
