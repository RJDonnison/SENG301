# TDD

Test-Driven Development (TDD) is a software development approach where tests are written before the production code. It follows a short, repetitive cycle known as **Red-Green-Refactor**.

## The Cycle

1.  **Red:** Write a failing test that defines a desired improvement or new function.
2.  **Green:** Write the minimal amount of production code needed to make the test pass.
3.  **Refactor:** Clean up the code while keeping all tests passing.

## Benefits

*   **Fewer Bugs:** Writing tests first forces you to think about edge cases and expected behavior upfront.
*   **Better Design:** TDD encourages loose coupling and testable architecture.
*   **Living Documentation:** Tests serve as executable specifications that stay in sync with the code.
*   **Safe Refactoring:** A comprehensive test suite gives confidence to restructure code without breaking functionality.
*   **Faster Feedback:** Failures are caught immediately rather than later in the development cycle.

## Principles

*   **Keep tests independent:** Each test should be runnable in isolation.
*   **Test one thing per test:** Each test should verify a single behavior.
*   **Write the simplest thing:** Write just enough production code to pass the test — no more.
*   **Don't write code without a failing test:** All production code is driven by a test.
