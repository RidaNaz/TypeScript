In TypeScript, typing can be handled implicitly or explicitly depending on how you declare and use variables, function parameters, and return types.

# Implicit Typing
- Implicit typing refers to TypeScript's ability to infer the type of a variable based on its initialization.
- TypeScript uses the value assigned to a variable to determine its type, without explicitly specifying the type using annotations.

## Examples of Implicit Typing:

```ts
// basic types
let name = "Alice"; // `name` is inferred as `string`
let count = 42;     // `count` is inferred as `number`
let isActive = true; // `isActive` is inferred as `boolean`

// arrays
let numbers = [1, 2, 3]; // `numbers` is inferred as `number[]`
let names = ["Alice", "Bob", "Charlie"]; // `names` is inferred as `string[]`

// objects
let person = {
    name: "Alice",
    age: 30
}; // `person` is inferred as `{ name: string, age: number }`
```

# Explicit Typing
- Explicit typing involves explicitly specifying the type of a variable, function parameter, or function return type using ***TypeScript annotations***.
- This is done by adding a colon (`:`) followed by the desired type.

## Examples of Explicit Typing:

```ts
// basic types
let username: string = "Alice";
let num: number = 42;
let active: boolean = true;

// arrays
let numbers: number[] = [1, 2, 3];
let names: string[] = ["Alice", "Bob", "Charlie"];

// objects
let person: { name: string, age: number } = {
    name: "Alice",
    age: 30
};

// functions 
function add(a: number, b: number): number {
    return a + b;
}

// union types
let id: string | number;
id = "abc"; // Valid
id = 123;   // Also valid
```


