# Mocking

Mocking is a technique used in testing to replace real dependencies with controlled substitutes, allowing tests to isolate the unit under test.

## Test Doubles

Test double is the generic term for any fake object used in place of a real one:

*   **Dummy:** Passed around but never actually used (e.g., to satisfy parameter lists).
*   **Fake:** A working implementation that is not production-ready (e.g., an in-memory database).
*   **Stub:** Provides canned answers to calls made during the test.
*   **Mock:** An object pre-programmed with expectations about which calls will be made and can verify that those expectations are met.
*   **Spy:** Wraps a real object and records which calls were made for later verification.

## When to Mock

*   When the real dependency is slow (database, network, file system).
*   When the real dependency is non-deterministic (randomness, current time).
*   When the real dependency is difficult to set up or tear down.
*   When you need to verify interactions between objects.

## Best Practices

*   Mock your own abstractions, not third-party code.
*   Prefer stubs (state verification) over mocks (behavior verification).
*   Avoid over-mocking — it makes tests brittle and coupled to implementation details.
*   Use dependency injection to make code testable with mocks.
