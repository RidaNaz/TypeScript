# Decorators
- In TypeScript, decorators provide a way to add annotations and metadata to classes, methods, properties, or parameters in a concise and reusable manner.
- They allow you to modify or extend the behavior of these elements at runtime or compile-time without directly modifying their source code.

## Using Decorators
To use decorators, you typically define a decorator function and then apply it to the target element using the `@` syntax. Here’s a basic example:

```ts
// Class decorator
function MyClassDecorator(target: Function) {
    // You can do something with the class constructor here
}

// Applying the decorator
@MyClassDecorator
class MyClass {
    // class implementation
}
```

- MyClassDecorator is a function that takes a constructor function as its parameter.
- @MyClassDecorator applies this decorator to the MyClass class.

## Types of Decorators
There are several types of decorators in TypeScript:

- **Class Decorators:** Applied to classes.
- **Method Decorators:** Applied to methods within a class.
- **Property Decorators:** Applied to properties of a class.
- **Parameter Decorators:** Applied to parameters of methods or constructors.

## Anatomy of a Decorator
A decorator function is a regular TypeScript function that takes specific parameters based on where it is applied:

### 1. Class Decorator:

```ts
function ClassDecorator<T extends { new(...args: any[]): {} }>(constructor: T) {
    return class extends constructor {
        // You can add new properties or methods here
    };
}
```

### 2. Method Decorator:

```ts
function MethodDecorator(target: any, propertyKey: string | symbol, descriptor: PropertyDescriptor) {
    // You can modify the method behavior using the descriptor
}
```

### 3. Property Decorator:

```ts
function PropertyDecorator(target: any, propertyKey: string | symbol) {
    // You can add metadata or modify the property here
}
```

### 4. Parameter Decorator:

```ts
function ParameterDecorator(target: any, propertyKey: string | symbol, parameterIndex: number) {
    // You can do something with the parameter here
}
```

