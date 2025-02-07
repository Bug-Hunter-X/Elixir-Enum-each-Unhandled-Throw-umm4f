# Elixir Enum.each Unhandled Throw

This repository demonstrates a common Elixir coding error involving the use of `throw` within `Enum.each` without proper exception handling.  The `Enum.each` function does not inherently handle exceptions thrown within its callback function.

The `bug.exs` file shows the problematic code.  The `bugSolution.exs` file presents a corrected version that uses a `try-catch` block to handle the thrown exception gracefully.

**Understanding the Issue:**

The `throw` macro halts execution immediately, leading to unexpected termination of your process if not handled appropriately within an appropriate construct. This behavior differs from functions that return values and raise exceptions differently.

**Solution:**

The provided solution wraps the `Enum.each` loop in a `try-catch` block. This allows you to catch the thrown exception, preventing program termination and implementing alternative handling (e.g., logging the error, retrying, or returning a specific value).

This example highlights the need to carefully handle exceptions, particularly in iterative processes like `Enum.each`, to ensure robustness in your Elixir applications.