# SOLID

SOLID is an acronym that defines good OO programming principles

## Single Responsibility Principle

A class should only have one responsibility. This reduces complexity and improves maintainability.

## Open/Closed Principle

A class should be open for extension but closed for modification. You can extend behavior via inheritance or composition without altering existing code.

## Liskov Substitution

Subclasses must be substitutable for their base classes. If S is a subtype of T, then objects of T should be replaceable with objects of S without altering program correctness.

## Interface Segregation

Clients should not be forced to depend on methods they don't use. Prefer small, focused interfaces over large, general-purpose ones.

## Dependency Inversion

High-level modules should not depend on low-level modules. Both should depend on abstractions, not concretions.
