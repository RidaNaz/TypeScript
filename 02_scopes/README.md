# Scopes 
## Lexical Scope
Lexical scope refers to the fact that the scope of a variable is determined by its location within the source code and nested functions have access to variables declared in their outer scope.

```ts
function outerFunction() {
    let outerVar = "I'm in the outer function";

    function innerFunction() {
        console.log(outerVar); // Accessible due to lexical scoping
    }

    innerFunction(); // Output: I'm in the outer function
}

outerFunction();
```
**Inner functions have access to variables declared in their outer scope.**
