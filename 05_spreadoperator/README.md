# Spread Operator
The spread operator (...) is a powerful feature that simplifies and enhances the readability of code involving arrays and objects in TypeScript.

## Arrays:
The spread operator can copy arrays, concatenate arrays, and add elements to arrays.

```ts
// copying arrays
let array1 = [1, 2, 3];
let array2 = [...array1]; // Spread elements of array1 into a new array

console.log(array2); // Output: [1, 2, 3]

// concatenating arrays
let array1 = [1, 2, 3];
let array2 = [4, 5, 6];
let concatenatedArray = [...array1, ...array2];

console.log(concatenatedArray); // Output: [1, 2, 3, 4, 5, 6]

// Adding Elements to an Array
let array = [1, 2, 3];
let newArray = [0, ...array, 4];

console.log(newArray); // Output: [0, 1, 2, 3, 4]
```

## Functions:
The spread operator can pass array elements as individual arguments to functions.

```ts
function add(a: number, b: number, c: number): number {
    return a + b + c;
}

let numbers = [1, 2, 3];
let sum = add(...numbers);

console.log(sum); // Output: 6
```

## Objects:
The spread operator can copy objects, merge objects, and add properties to objects.

```ts
// copying objects
et obj1 = { a: 1, b: 2 };
let obj2 = { ...obj1 };

console.log(obj2); // Output: { a: 1, b: 2 }

// merging objects
let obj1 = { a: 1, b: 2 };
let obj2 = { b: 3, c: 4 };
let mergedObj = { ...obj1, ...obj2 };

console.log(mergedObj); // Output: { a: 1, b: 3, c: 4 }

// Adding Properties to an Object
let obj = { a: 1, b: 2 };
let extendedObj = { ...obj, c: 3 };

console.log(extendedObj); // Output: { a: 1, b: 2, c: 3 }
```

## Destructuring:
The spread operator can be combined with destructuring to extract elements or properties while keeping the rest.

## 1. Array Destructuring
```ts
let numbers = [1, 2, 3, 4, 5];
let [first, ...rest] = numbers;

console.log(first); // Output: 1
console.log(rest);  // Output: [2, 3, 4, 5]
```

## 2. Object Destructuring
```ts
let obj = { a: 1, b: 2, c: 3 };
let { a, ...rest } = obj;

console.log(a);    // Output: 1
console.log(rest); // Output: { b: 2, c: 3 }
```