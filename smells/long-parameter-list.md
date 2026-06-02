# Long Parameter List

A method has too many parameters, often caused when two algorithms are merged or when related data is not grouped. See [Types](/smells/types.md).

### Refactoring

Use Introduce Parameter Object, Preserve Whole Object, or Replace Parameter with Method Call.

## Example

```python
def create_event(title, start_date, start_time, end_date, end_time, location, description, organizer_email, organizer_name, is_public, max_attendees):
    ...
```

## Refactored

```python
@dataclass
class DateTimeRange:
    start_date: str
    start_time: str
    end_date: str
    end_time: str

@dataclass
class Organizer:
    name: str
    email: str

def create_event(title, when: DateTimeRange, location, description, organizer: Organizer, is_public, max_attendees):
    ...
```
