# Truthy and Falsy Values
In TypeScript, values are categorized as either ***"truthy" or "falsy"***. These categories determine how values are evaluated in Boolean contexts, such as conditional statements (`if, while, for`), logical operators (`&&, ||`), and ternary operators (`? :`).

## Falsy Values
A falsy value is a value that is considered false when evaluated in a Boolean context. There are only a few falsy values in TypeScript:

- false: The Boolean value false.
- 0: The number zero.
- -0: The number negative zero.
- 0n: The BigInt value zero.
- "": An empty string.
- null: The absence of any value.
- undefined: A variable that has been declared but not assigned a value.
- NaN: The result of an invalid number operation.

In a Boolean context, all these values will be treated as false.

```ts
if (false) {
    console.log("This will not be logged");
}

if (0) {
    console.log("This will not be logged");
}

if (-0) {
    console.log("This will not be logged");
}

if (0n) {
    console.log("This will not be logged");
}

if ("") {
    console.log("This will not be logged");
}

if (null) {
    console.log("This will not be logged");
}

if (undefined) {
    console.log("This will not be logged");
}

if (NaN) {
    console.log("This will not be logged");
}
```

## Truthy Values
A truthy value is any value that is not falsy. This means that truthy values include everything that is not in the list of falsy values mentioned above. Some common truthy values include:

- true: The Boolean value true.
- Non-zero numbers: Any number other than 0 or -0 (e.g., 1, -1, 2.5).
- Non-empty strings: Any string with at least one character (e.g., "hello", " ").
- Objects: Including arrays and functions (e.g., {}, [], function() {}).
- Non-zero BigInt values: Any BigInt value other than 0n (e.g., 1n, -1n).

In a Boolean context, all these values will be treated as true.

```ts
if (true) {
    console.log("This will be logged");
}

if (1) {
    console.log("This will be logged");
}

if (-1) {
    console.log("This will be logged");
}

if (2.5) {
    console.log("This will be logged");
}

if ("hello") {
    console.log("This will be logged");
}

if (" ") {
    console.log("This will be logged");
}

if ({}) {
    console.log("This will be logged");
}

if ([]) {
    console.log("This will be logged");
}

if (function() {}) {
    console.log("This will be logged");
}

if (1n) {
    console.log("This will be logged");
}
```

### Example: Logical Operators
Logical operators often take advantage of truthy and falsy values.

- AND (&&): Returns the first falsy value or the last value if none are falsy.
- OR (||): Returns the first truthy value or the last value if none are truthy.

```ts
const a = 0;
const b = "hello";

const result1 = a || b; // "hello" (0 is falsy, "hello" is truthy)
const result2 = a && b; // 0 (0 is falsy, so it returns the first falsy value)

console.log(result1); // Output: "hello"
console.log(result2); // Output: 0
```

### Example: Default Values with ||
Using || to provide default values when a variable is falsy:

```ts
function greet(name?: string) {
    name = name || "Guest";
    console.log(`Hello, ${name}`);
}

greet(); // Output: "Hello, Guest" (undefined is falsy, so "Guest" is used)
greet("Alice"); // Output: "Hello, Alice"
```