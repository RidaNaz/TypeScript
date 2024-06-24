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

##### In TypeScript, lexical scope is governed by the following rules:

- Variables declared inside a function are only accessible within that function.
- Variables declared outside a function are accessible from anywhere within the same file.
- Variables declared inside a block (e.g., if statement or loop) are only accessible within that block.