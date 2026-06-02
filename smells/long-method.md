# Long Method

A method contains too many lines of code, making it difficult to understand, test, and maintain. See [Types](/smells/types.md).

### Refactoring

Use Extract Method to move blocks of code into smaller, well-named methods.

## Example

```python
def process_order(order):
    print("Processing order...")
    total = 0
    for item in order["items"]:
        total += item["price"] * item["quantity"]
    if total > 100:
        total *= 0.9
    tax = total * 0.08
    total += tax
    print(f"Subtotal: {total - tax}")
    print(f"Tax: {tax}")
    print(f"Total: {total}")
    order["total"] = total
    save_to_database(order)
    send_confirmation_email(order)
```

## Refactored

```python
def process_order(order):
    print("Processing order...")
    total = calculate_total(order)
    total = apply_tax_and_discount(total)
    order["total"] = total
    save_to_database(order)
    send_confirmation_email(order)

def calculate_total(order):
    return sum(item["price"] * item["quantity"] for item in order["items"])

def apply_tax_and_discount(total):
    if total > 100:
        total *= 0.9
    tax = total * 0.08
    print(f"Subtotal: {total}")
    print(f"Tax: {tax}")
    total += tax
    print(f"Total: {total}")
    return total
```
