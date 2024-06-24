# Types in TypeScript
## Basic types
Along with Primitive types here are some other types in TypeScript that falls in basic category:

### 1. [Array](/06_arraymethods/README.md)
Represents a collection of values. Can be defined in two ways:

* Array type literal: `elementType[]`
* Generic array type: `Array<elementType>`

```ts
let list: number[] = [1, 2, 3];
let genericList: Array<number> = [1, 2, 3];
```

### 2. [Tuple](/01_datatypes/typescript/tuples/README.md)
Represents an array with a fixed number of elements where each element can have a different type.

```ts
let x: [string, number];
x = ["hello", 10]; // OK
x = [10, "hello"]; // Error
```

### 3. [Enum](/01_datatypes/typescript/enums/README.md)
Represents a collection of related values that can be numeric or string-based.

```ts
enum Color { Red, Green, Blue }
let c: Color = Color.Green;
```

### 4. any
Represents any type, bypassing type checking. Useful for dynamic content.

```ts
let notSure: any = 4;
notSure = "maybe a string instead";
notSure = false;
```

### 8. void
Represents the absence of any type. Commonly used as the return type of functions that do not return a value.

```ts
function warnUser(): void {
    console.log("This is my warning message");
}
```

## Advanced Types
### 1. Union
Represents a value that can be one of several types.

```ts
let value: string | number;
value = "hello";
value = 42;
```

### 2. Intersection
Combines multiple types into one.

```ts
interface Draggable {
    drag(): void;
}

interface Resizable {
    resize(): void;
}

type UIElement = Draggable & Resizable;

let button: UIElement = {
    drag() { console.log("Dragging"); },
    resize() { console.log("Resizing"); }
};
```

### 3. Type Aliases
Creates a new name for a type.

```ts
type Name = string;
type NameOrNumber = Name | number;
```

### 4. Interfaces
Describes the shape of an object, specifying its properties and types.

```ts
interface Person {
    name: string;
    age: number;
}

let john: Person = { name: "John", age: 25 };
```

### 5. Type Assertions
Allows you to override the inferred type.

```ts
let someValue: any = "this is a string";
let strLength: number = (someValue as string).length;
```

### 6. Literal Types
Represents exact values.

```ts
let specificString: "hello" = "hello";
type Direction = "up" | "down" | "left" | "right";
let dir: Direction = "up";
```

### 7. Type Guards
Used to perform runtime checks to ensure a value conforms to a certain type.

```ts
function isNumber(value: any): value is number {
    return typeof value === "number";
}

function getValue(value: string | number) {
    if (isNumber(value)) {
        return value.toFixed(2);
    }
    return value.toUpperCase();
}
```

### 8. Mapped Types
Creates new types by transforming properties of an existing type.

```ts
type Readonly<T> = {
    readonly [P in keyof T]: T[P];
};

interface User {
    id: number;
    name: string;
}

let readonlyUser: Readonly<User> = { id: 1, name: "John" };
// readonlyUser.id = 2; // Error: Cannot assign to 'id' because it is a read-only property.
```

## Generic Types
Generics allow you to create reusable components that work with a variety of types.

```ts
function identity<T>(arg: T): T {
    return arg;
}

let output = identity<string>("myString"); // Output: "myString"
```
### Generic Interfaces

```ts
interface GenericIdentityFn<T> {
    (arg: T): T;
}

function identity<T>(arg: T): T {
    return arg;
}

let myIdentity: GenericIdentityFn<number> = identity;
```