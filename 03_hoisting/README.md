
## Hoisting:
*JavaScript's behavior* of moving variable and function declarations to the top of their containing scope before code execution. Only declarations are hoisted, not initializations.

1. **Declarations:**   Variable and function declarations are hoisted to the top of their scope.

2. **Initializations:** Initializations are not hoisted. Variables declared with var are initialized with undefined. Variables declared with let and const are not initialized.

```ts
console.log(x); // Output: undefined
var x = 5;
console.log(x); // Output: 5

console.log(y); // ReferenceError: Cannot access 'y' before initialization
let y = 10;

console.log(z); // ReferenceError: Cannot access 'z' before initialization
const z = 15;
```

3. **Temporal Dead Zone:**   Variables declared with let and const cannot be accessed before their declaration, leading to a ReferenceError.

4. **Function Declarations:**   Both the declaration and the definition are hoisted, allowing functions to be called before they appear in the code.

```ts
console.log(myFunction()); // Output: Hello, world!

function myFunction() {
    return "Hello, world!";
}
```

5. **Function Expressions:**   Only the variable declaration is hoisted, not the assignment, leading to potential TypeError if called before assignment.