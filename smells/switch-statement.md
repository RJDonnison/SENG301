# Switch Statement

A complex sequence of if-else or switch logic that must be modified whenever a new condition is added, violating the Open/Closed Principle. See [Types](/smells/types.md).

### Refactoring

Isolate the logic with Extract Method and Move Method. If based on type, use Replace Conditional with Polymorphism or Replace Type Code with Subclasses.

## Example

```python
def calculate_shipping(weight, method):
    if method == "standard":
        return weight * 0.5
    elif method == "express":
        return weight * 1.5 + 5
    elif method == "overnight":
        return weight * 3.0 + 10
    elif method == "international":
        return weight * 5.0 + 20
    else:
        raise ValueError("Unknown method")
```

## Refactored

```python
from abc import ABC, abstractmethod

class ShippingMethod(ABC):
    @abstractmethod
    def calculate(self, weight):
        ...

class StandardShipping(ShippingMethod):
    def calculate(self, weight):
        return weight * 0.5

class ExpressShipping(ShippingMethod):
    def calculate(self, weight):
        return weight * 1.5 + 5

class OvernightShipping(ShippingMethod):
    def calculate(self, weight):
        return weight * 3.0 + 10

def calculate_shipping(weight, method: ShippingMethod):
    return method.calculate(weight)
```
