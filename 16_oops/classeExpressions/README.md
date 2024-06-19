# Class Expression
In TypeScript, class expressions provide a way to define classes using expressions rather than declarations. This gives you more flexibility in defining classes dynamically at runtime or in scenarios where class definitions need to be generated programmatically. Class expressions are similar to function expressions in JavaScript.

### Syntax
The syntax for a class expression is straightforward:

```ts
const MyClass = class {
    // class implementation
};
```

Here, MyClass is a variable that holds an unnamed class expression. The class can have methods, properties, and constructors just like a regular class declaration.

## Features and Usage

### 1. Unnamed Classes
Class expressions allow you to create classes without explicitly naming them. This can be useful when you need to create classes on the fly or pass them as arguments to functions:

```ts
const Rectangle = class {
    constructor(public width: number, public height: number) {}

    getArea(): number {
        return this.width * this.height;
    }
};

const rect = new Rectangle(5, 10);
console.log(rect.getArea()); // Output: 50
```

### 2. Named Classes
You can also name class expressions if needed:

```ts
const NamedRectangle = class Rectangle {
    constructor(public width: number, public height: number) {}

    getArea(): number {
        return this.width * this.height;
    }
};

const namedRect = new NamedRectangle(7, 3);
console.log(namedRect.getArea()); // Output: 21
```
