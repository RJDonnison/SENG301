# PlantUML Cheatsheet

## Table of Contents

1. [Getting Started](#getting-started)
2. [Class Diagrams](#class-diagrams)
3. [Sequence Diagrams](#sequence-diagrams)
4. [Use Case Diagrams](#use-case-diagrams)
5. [Activity Diagrams](#activity-diagrams)
6. [Component Diagrams](#component-diagrams)
7. [State Diagrams](#state-diagrams)
8. [Skinparam & Styling](#skinparam--styling)
9. [Worked Example — Command Pattern](#worked-example--command-pattern)

---

## Getting Started

Every diagram is wrapped in `@startuml` / `@enduml`.

```plantuml
@startuml
' This is a comment
Alice -> Bob : Hello
@enduml
```

---

## Class Diagrams

### Declaring Classes

```plantuml
@startuml

' Plain class
class Animal {
  - name: String
  # age: int
  + speak(): void
  ~ package_method(): void
}

' Abstract class
abstract class Shape {
  + {abstract} area(): double
}

' Interface
interface Flyable {
  + fly(): void
}

' Enum
enum Direction {
  NORTH
  SOUTH
  EAST
  WEST
}

' Annotation
annotation MyAnnotation

@enduml
```

### Visibility Modifiers

| Symbol | Visibility |
| ------ | ---------- |
| `-`    | private    |
| `#`    | protected  |
| `+`    | public     |
| `~`    | package    |

### Relationships

```plantuml
@startuml

' Extension (inheritance)
Dog --|> Animal

' Implementation (interface)
Bird ..|> Flyable

' Composition (strong ownership)
Car *-- Engine

' Aggregation (weak ownership)
Library o-- Book

' Association (uses)
Teacher --> Student

' Dependency (dashed uses)
Client ..> Service

' Realisation (dashed + open triangle)
Impl ..|> Interface

@enduml
```

### Relationship Labels & Multiplicity

```plantuml
@startuml

' Label on arrow
Teacher "1" --> "many" Student : teaches

' Navigability
A --> B : uses >
A <-- B : used by <

' Bidirectional
A <--> B

@enduml
```

---

## Worked Example — Command Pattern

The diagram below maps directly to the GoF Command pattern as applied to a text editor, with the full tabular mapping:

| GoF Term         | Our Design     |
| ---------------- | -------------- |
| Client           | `UI`           |
| Invoker          | `Button`       |
| Command          | `Command`      |
| Concrete Command | `CopyCommand`  |
| Concrete Command | `PasteCommand` |
| Concrete Command | `UndoCommand`  |
| Receiver         | `TextEditor`   |

```plantuml
@startuml

class UI <<Client>> {
  + render()
}

class Button <<Invoker>> {
  - command: Command
  + setCommand(c: Command)
  + onClick()
}

interface Command <<interface>> {
  + execute(): void
}

class CopyCommand <<Concrete Command>> {
  - editor: TextEditor
  + execute(): void
}

class PasteCommand <<Concrete Command>> {
  - editor: TextEditor
  + execute(): void
}

class UndoCommand <<Concrete Command>> {
  - editor: TextEditor
  + execute(): void
}

class TextEditor <<Receiver>> {
  + display(): void
  + amendText(): void
  + deleteText(): void
  + undo(): void
}

UI ..> Button : creates
UI ..> TextEditor : renders

Button o--> Command : uses
CopyCommand  ..|> Command
PasteCommand ..|> Command
UndoCommand  ..|> Command
CopyCommand  --> TextEditor : calls
PasteCommand --> TextEditor : calls
UndoCommand  --> TextEditor : calls

@enduml
```

### Arrow Quick Reference

| Syntax | Meaning                        | Line style             |
| ------ | ------------------------------ | ---------------------- | ------------------ |
| `--    | >`                             | Inheritance / extends  | solid + filled tri |
| `..    | >`                             | Implements interface   | dashed + open tri  |
| `-->`  | Association / calls            | solid arrow            |
| `..>`  | Dependency / creates           | dashed arrow           |
| `o-->` | Aggregation (weak ownership)   | solid + open diamond   |
| `*-->` | Composition (strong ownership) | solid + filled diamond |
| `<-->` | Bidirectional association      | solid double arrow     |

> **Tip:** Reverse any arrow by flipping the direction: `B --|> A` draws the triangle pointing at A.
