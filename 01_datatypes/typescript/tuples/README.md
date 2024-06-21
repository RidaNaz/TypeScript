# Tuples
Tuples are a special type of array in TypeScript that allows you to specify the types of elements at specific positions.
They provide a way to represent an array with a fixed number of elements where each element can have a different type.

## Defining Tuples

```ts
let tuple: [string, number, boolean];
tuple = ["hello", 42, true]; // This is valid
// tuple = [42, "hello", true]; // This would cause a type error
```

## Tuples with Optional and Rest Elements

```ts
let tuple: [string, number?];
tuple = ["hello"];
tuple = ["hello", 42];

let tupleWithRest: [string, ...number[]];
tupleWithRest = ["hello", 1, 2, 3, 4];
```