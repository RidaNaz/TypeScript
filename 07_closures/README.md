# Closures:
A closure is a feature in programming languages where an inner function has access to the outer (enclosing) function's variables. This access is preserved even after the outer function has finished executing. In other words, a closure allows a function to access variables from an enclosing scope ([lexical scope](/02_scopes/README.md#lexical-scope)) even after the function has finished executing and those variables are no longer in scope.

## Example

```ts
function outerFunction(outerValue: number) {
    // This inner function is a closure because it captures `outerValue`.
    function innerFunction(innerValue: number): number {
        return outerValue + innerValue;
    }
    return innerFunction;
}

let addFive = outerFunction(5); // `addFive` now holds the inner function with `outerValue` as 5

console.log(addFive(3)); // Output: 8
console.log(addFive(10)); // Output: 15
```

- **Usage of addFive:**
addFive is now a closure because it "closes over" or captures the variable outerValue from its lexical scope (outerFunction).

When `addFive(3)` is called, it accesses outerValue (which is 5) and computes 5 + 3, resulting in 8.
Similarly, `addFive(10)` computes 5 + 10, resulting in 15.

## Benefits of Closures in TypeScript:
* Data Encapsulation: Closures help encapsulate data within functions, preventing unintended modification by other parts of the program.

* Stateful Functions: They allow functions to maintain state between successive calls without exposing that state to the outside world.

* Functional Programming: Closures are fundamental to many functional programming concepts like currying and memoization.

## Considerations:
* Memory Management: Closures can hold references to outer variables, potentially keeping them alive longer than expected, which may affect memory usage if not managed properly.

* Performance: While closures are powerful, excessive use or misuse (like creating too many nested closures unnecessarily) can impact performance.

* **Lexical scope is about the physical location of variables and their accessibility.**
* **Closures are functions that have access to their own scope and the scope of their parent functions.**