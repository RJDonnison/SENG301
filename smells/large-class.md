# Large Class

A class has too many lines, properties, or methods, indicating it is doing too much and violating the Single Responsibility Principle. See [Types](/smells/types.md).

### Refactoring

Use Extract Class to split responsibilities into separate, focused classes.

## Example

```python
class Report:
    def __init__(self):
        self.data = []
        self.format = "pdf"
        self.header = ""
        self.footer = ""
        self.margins = (1, 1, 1, 1)
        self.font = "Arial"
        self.font_size = 12
        self.filename = ""
        self.connection = None

    def fetch_data(self):
        ...

    def generate_pdf(self):
        ...

    def generate_csv(self):
        ...

    def send_email(self):
        ...

    def archive_report(self):
        ...
```

## Refactored

```python
class ReportData:
    def __init__(self):
        self.data = []
        self.source = ""

    def fetch(self):
        ...

class ReportFormatter:
    def __init__(self):
        self.format = "pdf"
        self.font = "Arial"
        self.font_size = 12

    def generate(self, data):
        ...

class ReportDelivery:
    def send_email(self, report):
        ...

    def archive(self, report):
        ...
```
