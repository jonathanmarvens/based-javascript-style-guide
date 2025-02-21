# Based JavaScript/TypeScript Style Guide

Short and sweet rules and patterns that yield predictable and optimized JavaScript code execution while keeping the codebase clean and maintainable.

**Author:** Jonathan Barronville

## 1. Naming Conventions

- **Variables & Functions:** Use `camelCase` for variables and functions.
- **Classes & Interfaces:** Use `PascalCase`.
- **Constants:** Use `const` with `camelCase` (or `UPPER_SNAKE_CASE` if you prefer for globals).

## 2. TypeScript Guidelines

- **Explicit Types:** Annotate function parameters, return types, and complex variable types.
- **Interfaces & Type Aliases:** Use interfaces to define object shapes and type aliases for unions/intersections.
- **Avoid `any`:** Use `unknown` or precise types to enforce type safety.
- **Utility Types:** Utilize built-in utilities (_e.g._, `Partial`, `Readonly`, `Pick`) for clear data transformations.

## 3. Object Shape & Data Structures

- **Stable Objects:** Initialize objects with all expected properties in constructors or factory functions.
- **No Dynamic Property Changes:** Avoid adding or deleting properties at runtime.
- **Consistent Structures:** Leverage interfaces to guarantee a stable object shape, enabling inline caching and hidden class optimizations.

## 4. Function Design

- **Small & Focused:** Each function should have a single responsibility and do one thing well.
- **Monomorphic Calls:** Ensure function parameters consistently use the same types to help JIT optimizations.
- **Limited Parameters:** Keep the parameter count low (prefer wrapping multiple parameters in an object when needed).
- **Pure Functions:** Favor functions without side effects to improve testability and enable compiler optimizations.

## 5. Control Flow & Loops

- **Early Returns:** Use early exits to reduce nesting and clarify logic.
- **Simple Loop Constructs:** Prefer classic loops or array methods (`for`, `forEach`, `map`) that are friendly to JIT inline caching.
- **Minimal Branches:** Keep conditional logic straightforward; avoid deeply nested conditionals that complicate predictability.

## 6. Asynchronous Patterns

- **Async/Await:** Use `async`/`await` for clean and non-blocking code instead of complex promise chains or nested callbacks.
- **Error Handling:** Use `try`/`catch` blocks around asynchronous code to maintain clarity in error paths.

## 7. Immutability & Variable Declarations

- **Const by Default:** Declare variables as `const` unless mutation is required.
- **Immutable Data:** Favor immutability; use the spread operator or utility functions to create new objects instead of mutating existing ones.

## 8. Engine-Friendly Patterns

- **Stable Data Types:** Ensure that functions receive consistent types throughout their lifecycle.
- **Avoid Dynamic Code:** Do not use `eval`, dynamic property accesses, or overly generic metaprogramming patterns that can inhibit JIT optimization.
- **Optimize Hot Paths:** Write clear and tight loops for performance-critical code, and use simple arithmetic and property accesses.

## 9. Formatting & Readability

- **Indentation:** Use consistent indentation (2 or 4 spaces) throughout the code.
- **Line Length:** Keep lines within 80–120 characters.
- **Braces & Spacing:** Always use braces for conditionals and loops, and place spaces around operators for clarity.
- **Logical Grouping:** Separate code sections with blank lines to visually group related logic.

## 10. Comments & Inline Documentation

- **Explain "Why", Not "What":** Comments should clarify intent and reasoning, not restate the code.
- **Keep It Sparse:** Rely on self-explanatory code; only add comments where complex logic is unavoidable.

## Final Tips

- **Profile Before Optimizing:** Measure performance-critical code paths; focus on clarity first.
- **Trust the Engine:** Write straightforward, monomorphic code, and let modern runtimes apply aggressive optimizations.
- **Refactor Regularly:** Continuously improve code readability and structure to prevent hidden performance traps.
