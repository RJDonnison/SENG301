# Speculative Generality

"Just in case" code written for future scenarios that may never materialize, adding unnecessary complexity. See [Types](/smells/types.md).

### Refactoring

Remove the over-engineering. Only add flexibility when it is actually needed.

## Example

```python
class ReportGenerator:
    def generate(self, data, format="pdf"):
        if format == "pdf":
            self._generate_pdf(data)
        elif format == "csv":
            self._generate_csv(data)
        elif format == "html":
            self._generate_html(data)
        elif format == "xml":
            self._generate_xml(data)
        elif format == "json":
            self._generate_json(data)
        else:
            raise ValueError("Unknown format")

    def _generate_xml(self, data):
        ...

    def _generate_json(self, data):
        ...
```

(xml and json formats are never used.)

## Refactored

```python
class ReportGenerator:
    def generate(self, data, format="pdf"):
        if format == "pdf":
            self._generate_pdf(data)
        elif format == "csv":
            self._generate_csv(data)
        elif format == "html":
            self._generate_html(data)
        else:
            raise ValueError("Unknown format")
```
