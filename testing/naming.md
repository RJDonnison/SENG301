# Naming

Clear and consistent test naming is essential for understanding what a test covers and diagnosing failures quickly.

## Conventions

A well-structured test name typically follows the pattern:

`[UnitOfWork]_[Scenario]_[ExpectedBehavior]`

*   **Unit of Work:** The method or feature being tested.
*   **Scenario:** The condition or input under which the test runs.
*   **Expected Behavior:** What the test expects to happen.

## Examples

*   `calculateTotal_withEmptyCart_returnsZero`
*   `divide_byZero_throwsException`
*   `submitOrder_withInvalidPayment_rejectsOrder`

## Principles

*   **Descriptive:** The name should read like a sentence and explain the test's purpose without needing to read the body.
*   **Consistent:** Use the same naming pattern across the entire project.
*   **Searchable:** Names should be easy to find with grep or IDE search tools.
*   **Stable:** Avoid including implementation details in names that are likely to change.
