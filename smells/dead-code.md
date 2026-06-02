# Dead, Unreachable, or Commented Code

Code that is never executed (dead), cannot be reached (unreachable), or has been commented out. It adds clutter, confusion, and maintenance overhead. See [Types](/smells/types.md).

### Refactoring

Delete the code. Version control will preserve it if needed later.

## Example

```python
def process_payment(amount):
    # old_rate = 1.2
    # if currency == "EUR":
    #     amount *= old_rate
    if amount > 0:
        charge(amount)
    calculate_fees()
    return True
    send_receipt()  # Never reached
```

## Refactored

```python
def process_payment(amount):
    if amount > 0:
        charge(amount)
    calculate_fees()
    send_receipt()
    return True
```
