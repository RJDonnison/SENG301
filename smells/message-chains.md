# Message Chains

Occurs when a client requests an object, which requests another object, which requests yet another, creating tight coupling to the complete navigation path. See [Types](/smells/types.md).

### Refactoring

Use Hide Delegate so that the client only depends on its direct neighbor.

## Example

```python
def get_customer_city(order):
    return order.get_customer().get_address().get_city()
```

## Refactored

```python
class Order:
    def get_customer_city(self):
        return self._customer.get_city()

class Customer:
    def get_city(self):
        return self._address.get_city()

class Address:
    def get_city(self):
        return self._city
```
