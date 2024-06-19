# Optional chaining
Optional chaining is a feature in TypeScript that allows you to safely access deeply nested properties of an object without having to explicitly check for the existence of each reference in the chain. This can greatly simplify code by reducing the need for repetitive and cumbersome null checks.

### Syntax
The optional chaining operator is `?.`. It can be used at any point in a chain of property accesses to stop evaluation and return undefined if the value before it is null or undefined.

### Example
```ts
interface User {
    name: string;
    address?: {
        street?: {
            name?: string;
        };
    };
}

const user: User = {
    name: "Alice"
};

// Without optional chaining
const streetName = user.address && user.address.street && user.address.street.name;
console.log(streetName); // Output: undefined

// With optional chaining
const streetNameWithOptionalChaining = user.address?.street?.name;
console.log(streetNameWithOptionalChaining); // Output: undefined
```

## 1. Optional Chaining with Functions
Optional chaining can also be used to call methods that might not exist:

```ts
interface User {
    name: string;
    getAddress?: () => string;
}

const user: User = {
    name: "Alice"
};

// Without optional chaining
const address = user.getAddress ? user.getAddress() : undefined;
console.log(address); // Output: undefined

// With optional chaining
const addressWithOptionalChaining = user.getAddress?.();
console.log(addressWithOptionalChaining); // Output: undefined
```

- Here, `user.getAddress?.()` safely attempts to call getAddress if it exists. If getAddress is undefined, the call is not made, and undefined is returned.

## 2. Optional Chaining with Arrays
You can also use optional chaining to access elements in an array that might not exist:

```ts
const users: User[] = [{ name: "Alice" }, { name: "Bob", address: { street: { name: "Main St" } } }];

// Without optional chaining
const streetName = users[1] && users[1].address && users[1].address.street && users[1].address.street.name;
console.log(streetName); // Output: Main St

// With optional chaining
const streetNameWithOptionalChaining = users[1]?.address?.street?.name;
console.log(streetNameWithOptionalChaining); // Output: Main St
```

- In this example, `users[1]?.address?.street?.name` safely navigates the nested structure, returning undefined if any part of the chain is undefined.

## 3. Combining Optional Chaining with Nullish Coalescing
The nullish coalescing operator (??) can be used in conjunction with optional chaining to provide a default value if the result of the optional chain is undefined or null:

```ts
const user: User = {
    name: "Alice"
};

const streetName = user.address?.street?.name ?? "No street name provided";
console.log(streetName); // Output: No street name provided
```

- In this example, if `user.address?.street?.name` evaluates to undefined, the default value "No street name provided" is used.
