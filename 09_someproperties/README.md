# 1. charAt()
The charAt() method is used to get the character at a specified index (position) within a string. The index starts at 0.

```ts
let str = "Hello";
console.log(str.charAt(0)); // Output: "H"
console.log(str.charAt(3)); // Output: "l"
console.log(str.charAt(10)); // Output: ""
```

# 2. NaN
NaN stands for "Not-a-Number" and represents a value that is not a valid number according to the JavaScript/TypeScript specification. It is returned when a mathematical operation or function that expects a number receives something that is not a number.

```ts
let result = parseInt("abc"); // result is NaN because "abc" cannot be converted to a number
console.log(result); // Output: NaN

console.log(typeof NaN); // Output: "number"
console.log(NaN === NaN); // Output: false (NaN is not equal to itself)
```

# 3. parseInt()
The parseInt() function parses a string argument and returns an integer of the specified radix (base). If the radix is not specified, JavaScript assumes it to be 10 (decimal).

```ts
parseInt(string, radix?)
```

string: The string to parse into an integer.
radix: An optional integer between 2 and 36 that represents the numeral system to be used (e.g., binary, octal, decimal, hexadecimal).

```ts
let numStr = "123";
let num = parseInt(numStr);
console.log(num); // Output: 123

let binaryStr = "1010";
let binaryNum = parseInt(binaryStr, 2);
console.log(binaryNum); // Output: 10
```
# 4. toString()
The toString() method converts a number to a string. It can also be used with other data types such as booleans and objects to convert them into string representations.

```ts
num.toString(radix?)
```

num: The number or object to convert to a string.
radix: An optional integer between 2 and 36 specifying the base to use for representing numeric values.

```ts
let num = 123;
let numStr = num.toString();
console.log(numStr); // Output: "123"

let binNum = 10;
let binStr = binNum.toString(2);
console.log(binStr); // Output: "1010"
```

# 5. typeof
The typeof operator returns a string indicating the data type of its operand. It is often used to check the type of a variable or value at runtime.

```ts
let num = 42;
let str = "Hello";
let obj = { name: "John", age: 30 };

console.log(typeof num); // Output: "number"
console.log(typeof str); // Output: "string"
console.log(typeof obj); // Output: "object"
console.log(typeof NaN); // Output: "number"
console.log(typeof undefined); // Output: "undefined"
console.log(typeof true); // Output: "boolean"
console.log(typeof null); // Output: "object" (This is a quirk in JavaScript)
```

# 6. isNaN()
The isNaN() function determines whether a value is NaN (Not-a-Number) or not. It returns true if the value is NaN, and false otherwise.

```ts
console.log(isNaN(NaN)); // Output: true
console.log(isNaN(123)); // Output: false
console.log(isNaN("abc")); // Output: true (cannot be converted to a number)
console.log(isNaN(undefined)); // Output: true (undefined is not a number)
```