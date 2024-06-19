- In TypeScript, `Object.keys` and `Object.values` are methods available on the `Object`, global object that allow you to work with objects in a convenient and iterable manner.

- `Object.keys()` and `Object.values()` are useful utility methods in TypeScript for iterating over object properties in a straightforward manner. They facilitate tasks such as extracting keys or values for further processing, mapping over object properties, or performing operations on object data in a concise and efficient manner.

# Object.keys()
The `Object.keys()` method returns an array of a given object's own enumerable property names, in the same order as a `for...in` loop (the difference being that a `for...in` loop also iterates over inherited properties).

```ts
const obj = {
  name: 'John',
  age: 30,
  city: 'New York'
};

const keys = Object.keys(obj);
console.log(keys); // Output: ["name", "age", "city"]
```

Notes:
- `Object.keys()` returns an array of strings representing all the enumerable properties of the object.
- If obj is null or undefined, it will throw a TypeError.

# Object.values()
The `Object.values()` method returns an array of a given object's own enumerable property values, in the same order as `Object.keys()`.

```ts
const obj = {
  name: 'John',
  age: 30,
  city: 'New York'
};

const values = Object.values(obj);
console.log(values); // Output: ["John", 30, "New York"]
```

Notes:
- `Object.values()` returns an array containing the property values of the object in the same order as provided by a `for...in` loop (excluding inherited properties).
- If obj is null or undefined, it will throw a TypeError.

