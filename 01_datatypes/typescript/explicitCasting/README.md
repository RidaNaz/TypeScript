# Explicit Casting
Explicit casting in TypeScript, also known as type assertion, allows you to tell the TypeScript compiler that you know more about the type of a value than TypeScript can infer on its own.

## Syntax of Type Assertion
Type assertion in TypeScript has two forms:

### Angle-bracket syntax

```ts
let someValue: any = "this is a string";
let strLength: number = (<string>someValue).length;
```

### as syntax (Preferred method in TypeScript)

```ts
let someValue: any = "this is a string";
let strLength: number = (someValue as string).length;
```

* Both syntaxes are equivalent in terms of functionality, but the `as` syntax is recommended by TypeScript's style guide and generally considered more readable.

