# Divergent Change

Occurs when one class must be changed in many different ways for different reasons, indicating it has multiple responsibilities. See [Types](/smells/types.md).

### Refactoring

Use Extract Class to separate the class into distinct single responsibilities.

## Example

```python
class Employee:
    def calculate_pay(self):
        ...

    def report_hours(self):
        ...

    def save_to_database(self):
        ...

    def send_email(self):
        ...
```

## Refactored

```python
class Employee:
    ...

class PayCalculator:
    def calculate(self, employee):
        ...

class HourReporter:
    def report(self, employee):
        ...

class EmployeeRepository:
    def save(self, employee):
        ...
```
