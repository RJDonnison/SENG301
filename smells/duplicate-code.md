# Duplicate Code

The same problem is solved in multiple places, leading to maintenance burdens when a fix must be applied everywhere. See [Types](/smells/types.md).

### Refactoring

Consolidate logic using Extract Method and Move Method to centralize the duplicated behavior.

## Example

```python
def calculate_total_with_tax(items):
    subtotal = sum(item.price for item in items)
    tax = subtotal * 0.08
    return subtotal + tax

def calculate_total_with_discount(items):
    subtotal = sum(item.price for item in items)
    if subtotal > 100:
        subtotal *= 0.9
    return subtotal
```

## Refactored

```python
def calculate_subtotal(items):
    return sum(item.price for item in items)

def calculate_total_with_tax(items):
    subtotal = calculate_subtotal(items)
    return subtotal + subtotal * 0.08

def calculate_total_with_discount(items):
    subtotal = calculate_subtotal(items)
    return subtotal * 0.9 if subtotal > 100 else subtotal
```
