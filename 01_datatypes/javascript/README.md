# Primitive Types
Primitive data types are the most basic data types in TypeScript that comes from JavaScript. They are immutable, meaning their value cannot be changed once created.

1. **string:**  Represents text values.
```ts
let color: string = "blue";
color = 'red';
```

2. **Number:**  Represents both integer and floating-point numbers.
```ts
let decimal: number = 6;
let hex: number = 0xf00d;
let binary: number = 0b1010;
let octal: number = 0o744;
```

3. **boolean:**  Represents true/false values.
```ts
let isDone: boolean = false;
```

4. **Null:** Represents the intentional absence of any object value.
```ts
let emptyValue: null = null;
```

5. **Undefined:** Indicates a variable that has been declared but not yet assigned a value.
```ts
let notAssigned: undefined;
```

6. **BigInt:** Used for integers larger than the safe integer limit for the number type.
```ts
let bigIntNumber: bigint = 12345678901234567890n;
```

7. **Symbol:** Represents a unique, immutable identifier.
```ts
let uniqueId: symbol = Symbol('id');
```

# Non-primitive Types
Non-primitive types are more complex types and are derived from the primitive types. The main non-primitive types in JavaScript are:
* objects 
* arrays

## Differences Between Primitive and Non-Primitive Types
1. **Mutability**
- Primitive types are immutable.
- Non-primitive types are mutable.

2. **Reference vs Value**
- Primitive types are accessed by value.
- Non-primitive types are accessed by reference.

3. **Memory Allocation**
- Primitive types are stored directly in the memory location associated with the variable.
- Non-primitive types are stored as references pointing to the memory location where the object is stored.