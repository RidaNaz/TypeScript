# Enums
Enums (short for "enumerations") are a way to define a set of named constants. Enums allow you to define a collection of related values that can be numeric or string-based.

## Numeric Enums
By default, enums in TypeScript are numeric, starting at 0 and incrementing by 1 for each member:

```ts
enum Direction {
    Up,
    Down,
    Left,
    Right
}

let direction: Direction = Direction.Up;
console.log(direction); // Output: 0
```

You can also specify custom numeric values:

```ts
enum Direction {
    Up = 1,
    Down,
    Left,
    Right
}

console.log(Direction.Up);    // Output: 1
console.log(Direction.Down);  // Output: 2
```

## String Enums
String enums allow you to assign string values to enum members:

```ts
enum Direction {
    Up = "UP",
    Down = "DOWN",
    Left = "LEFT",
    Right = "RIGHT"
}

let direction: Direction = Direction.Left;
console.log(direction); // Output: LEFT
```

## Heterogeneous Enums
TypeScript also supports heterogeneous enums, which contain both string and numeric values:

```ts
enum MixedEnum {
    No = 0,
    Yes = "YES"
}

console.log(MixedEnum.No);  // Output: 0
console.log(MixedEnum.Yes); // Output: YES
```

