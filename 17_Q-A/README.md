# 1. Compile Time vs Runtime
Understanding the distinction between compile time and runtime is essential for working with TypeScript and other statically typed languages.

## Compile Time
Compile time refers to the period during which the TypeScript compiler processes the source code to produce JavaScript code. Several key activities happen at compile time:
1. Syntax Checking
2. Type Checking
3. Transpilation
4. Code Generation
5. Static Analysis

## Runtime
Runtime refers to the period when the generated JavaScript code is executed in a JavaScript environment (e.g., a web browser or Node.js). During runtime, the program performs the actual tasks defined in the code, such as manipulating the DOM, making network requests, or performing calculations.

## Differences Between Compile Time and Runtime

### Error Detection:
- Compile Time: Errors related to types, syntax, and other static constraints are detected. These errors prevent the code from being transpiled into JavaScript.
- Runtime: Errors related to the actual execution of the code, such as logic errors, runtime exceptions, and dynamic type issues.

### Performance:
- Compile Time: The focus is on validating and transpiling the code. Compile time performance is less critical in production but important for the development workflow.
- Runtime: Performance is critical since it affects the responsiveness and behavior of the application in production.

### Debugging:
- Compile Time: TypeScript provides detailed error messages and type information to help identify issues before the code runs.
- Runtime: Debugging involves using tools like the browser's developer console or Node.js debugger to inspect the behavior and state of the running application.

### Safety:
- Compile Time: TypeScript aims to catch as many errors as possible at compile time to enhance code safety and reliability.
- Runtime: Ensuring runtime safety involves thorough testing and handling unexpected conditions gracefully.

# 2. Modules
## JavaScript Modules
JavaScript has two primary module systems: *CommonJS* and *ECMAScript (ES)* modules.

### CommonJS
CommonJS is primarily used in Node.js environments. It uses require for importing modules and ***module.exports*** or ***exports*** for exporting them.

#### Example
> math.js (Module File)
```js
function add(a, b) {
    return a + b;
}

function subtract(a, b) {
    return a - b;
}

module.exports = { add, subtract };
app.js (Main File)
```

> app.js
```js
const math = require('./math');

console.log(math.add(2, 3));      // Output: 5
console.log(math.subtract(5, 3)); // Output: 2
```

## ECMAScript (ES) Modules
ES modules are the standardized module system introduced in ES6 (ECMAScript 2015). They use import for importing modules and export for exporting them. ES modules can be used both in browsers (with proper support) and in Node.js (from version 12+ with the .mjs extension or by setting *"type": "module"* in package.json).

### Loading
#### CommonJS:
Synchronous loading (blocking).
Suitable for server-side environments like Node.js.

#### ES Modules:
Asynchronous loading (non-blocking).
Suitable for both client-side (browsers) and server-side environments.

### Scope
#### CommonJS:
- Modules are loaded once and cached.
- Subsequent require calls return the cached module.

#### ES Modules:
- Modules are evaluated once and cached.
- Subsequent import calls return the cached module.

# 3. Is JavaScript Compiled or Interpreted
JavaScript has traditionally been considered an interpreted language, but modern JavaScript engines use a combination of interpretation and compilation techniques to execute code efficiently. Let's break down what this means:

## Interpreted Language
In an interpreted language, the source code is executed directly by an interpreter. The interpreter reads the code, parses it, and executes it line-by-line or statement-by-statement.

## Compiled Language
- In a compiled language, the source code is transformed by a compiler into machine code, which is then executed by the computer's CPU.
- This compilation step typically happens before the program is run, producing an executable file that can be distributed and run independently of the source code.

## Modern JavaScript Engines
Modern JavaScript engines, such as Google V8 (used in Chrome and Node.js), SpiderMonkey (used in Firefox), and JavaScriptCore (used in Safari), use a hybrid approach involving both *interpretation* and *just-in-time (JIT) compilation*. Here’s how it works:

# 4. Interpreter vs Compiler
## Interpreter
1. Execution: Interprets and executes code line-by-line or statement-by-statement.
2. Compilation Step: No separate compilation step; code is executed directly.
3. Error Detection: Errors are detected at runtime, often making debugging easier because the exact line of failure is known.
4. Performance: Typically slower than compiled code because of the overhead of interpreting the code on the fly.
5. Use Cases: Scripting languages like Python, JavaScript (traditional interpretation), Ruby.

## Compiler
1. Execution: Transforms source code into machine code (or intermediate code) that can be executed by the CPU.
2. Compilation Step: Involves a separate compilation step before execution, producing an executable file.
3. Error Detection: Errors are detected at compile-time, potentially leading to faster runtime performance since the code is pre-validated.
4. Performance: Generally faster than interpreted code because the machine code is optimized and executed directly by the CPU.
5. Use Cases: System programming languages like C, C++, Rust.

### Example of JavaScript Execution in Modern Engines

```ts
function add(a, b) {
    return a + b;
}

for (let i = 0; i < 1000000; i++) {
    add(i, i + 1);
}
```

***In a modern JavaScript engine:***

1. Parsing: The function add and the loop are parsed into an AST.
2. Bytecode: The AST is converted into bytecode and interpreted.
3. Profiling: The engine profiles the add function and the loop.
4. JIT Compilation: Since the add function is called many times, it is compiled into optimized machine code.
5. Execution: The optimized machine code is executed for subsequent calls, improving performance.

# 5. What is V8 Engine and How it Works?
V8 Engine is Google's open-source high-performance JavaScript and WebAssembly engine, written in C++. It is used in Google Chrome and Node.js.

## How V8 Works:

1. Parsing: V8 first parses JavaScript code and generates an Abstract Syntax Tree (AST).
2. Ignition Interpreter: The AST is then fed into the Ignition interpreter, which generates bytecode.
3. TurboFan JIT Compiler: V8 monitors the execution of the bytecode. Frequently executed code (hot code) is compiled into optimized machine code by the TurboFan Just-In-Time (JIT) compiler.
4. Garbage Collection: V8 includes efficient garbage collection mechanisms to manage memory by reclaiming memory occupied by objects that are no longer in use.

# 6. How Different Browsers Compile JavaScript to Binary Code?
Different browsers use their own JavaScript engines to compile JavaScript to binary code:

1. Chrome: Uses the V8 engine.
2. Firefox: Uses the SpiderMonkey engine.
3. Safari: Uses the JavaScriptCore engine (also known as Nitro).
4. Edge: Uses the Chakra engine (for legacy Edge) and V8 (for Chromium-based Edge).

These engines generally follow a similar approach:

1. Parsing: The JavaScript source code is parsed into an AST.
2. Bytecode: The AST is compiled into intermediate bytecode.
3. JIT Compilation: Frequently executed code is compiled into optimized machine code.

# 7. What is Node.js and How it Works?
Node.js is an open-source, cross-platform runtime environment that allows JavaScript to be run on the server side. It uses the V8 engine to execute JavaScript code outside of a browser.

## How it Works:

1. Event-Driven Architecture: Node.js uses an event-driven, non-blocking I/O model.
2. Single-Threaded: Node.js operates on a single thread using the event loop to handle asynchronous operations.
3. Modules: Node.js uses CommonJS modules to manage dependencies and modularize code.
4. Libuv: Node.js uses the libuv library to handle asynchronous I/O operations.

# 8. Is JavaScript Synchronous or Asynchronous by Default?
JavaScript is synchronous by default, executing code line by line. However, it has mechanisms (callbacks, promises, async/await) to handle asynchronous operations.

# 9. Sync vs Async
## Synchronous (Sync):
Executes code sequentially, blocking the next operation until the current one completes.

```ts
let result = func1(); let result2 = func2(result);
```

## Asynchronous (Async):
Executes code without waiting for operations to complete, allowing other tasks to run concurrently.

```ts
async function foo() {
    let result = await asyncFunc1();
    let result2 = await asyncFunc2(result); 
    }
```

# 10. Is Node.js Synchronous or Asynchronous by Default?
Node.js is asynchronous by default, using non-blocking I/O operations to handle concurrent tasks efficiently.

# 11. How JavaScript Handles Async Tasks?
JavaScript handles asynchronous tasks using:

- Callbacks: Functions passed as arguments to other functions, executed after a task completes.
- Promises: Objects representing the eventual completion or failure of an asynchronous operation.
- Async/Await: Syntactic sugar built on promises for writing asynchronous code in a synchronous style.

# 12. How Node.js Handles Async Tasks?
Node.js handles asynchronous tasks using:

- Event Loop: Manages the execution of asynchronous callbacks.
- Callbacks, Promises, and Async/Await: Similar to JavaScript in the browser.
- Libuv: Handles non-blocking I/O operations, managing thread pool and system-level operations.

# 13. What is Event Loop and How it Works?
Event Loop is a core part of the JavaScript runtime and Node.js, responsible for executing code, collecting and processing events, and executing queued sub-tasks.

## How it Works:

- Call Stack: Executes synchronous code.
- Task Queue: Holds asynchronous callbacks and promises resolved by the event loop.
- Event Loop: Continuously checks the call stack and task queue, executing tasks from the queue when the stack is empty.

# 14. What is npm and How it Works?
npm (Node Package Manager) is a package manager for Node.js, providing a way to install, share, and manage dependencies.

## How it Works:

- Package Installation: npm install package-name downloads and installs packages from the npm registry.
- Package Management: package.json file defines project dependencies and scripts.
- Version Control: Manages different versions of packages to ensure compatibility and stability.

# 15. Difference Between JSON and JavaScript Object
## JSON (JavaScript Object Notation):

- A lightweight data interchange format, text-based, and language-independent.
Syntax:
```ts
{"key": "value"}
```

- Used for data exchange between server and client.
Example:
```ts
{"name": "John", "age": 30}
```

## JavaScript Object:
- A data structure in JavaScript to store keyed collections and complex entities.
### Syntax:
```ts
{key: "value"}
```
- Used within JavaScript code to manipulate data.
```ts
let obj = {name: "John", age: 30};
```

# 16. What are Syntax Errors?
Syntax Errors are errors in the code that violate the rules of the programming language's syntax, preventing the code from being parsed correctly.

Example:

```ts
let x = 5 // Missing semicolon
if (x > 5 { // Missing closing parenthesis
    console.log("x is greater than 5");
    }
```

# 17. What are Type Errors?
Type Errors occur when a value is not of the expected type, causing runtime errors.

Example:

```ts
let num = 5;
num.toUpperCase(); // TypeError: num.toUpperCase is not a function
```

# 18. What are Assignability Errors?
Assignability Errors occur when a value is assigned to a variable that is not compatible with the variable's type. This is more common in statically typed languages or when using TypeScript.

Example:

```ts
let num: number;
num = "Hello"; // Error: Type 'string' is not assignable to type 'number'
```

# What are Threads in Programming?
Threads are the smallest unit of processing that can be scheduled by an operating system. A thread is a sequence of instructions within a program that can be managed independently by a scheduler.

# Is Node.js Single-Threaded or Multi-Threaded?
Node.js is single-threaded in its JavaScript execution model but uses a multi-threaded model under the hood for I/O operations via libuv.

# What is the Difference Between Single-Threaded and Multi-Threaded Languages?
## Single-Threaded:

- Executes one task at a time within a single thread.
- Simpler to implement and manage but can be less efficient for I/O-bound tasks.
- Example: JavaScript (in Node.js runtime for the JavaScript execution).

## Multi-Threaded:
- Can execute multiple tasks concurrently using multiple threads.
- More complex to implement and manage, but can handle CPU-bound and I/O-bound tasks more efficiently.
- Example: Java, C++ with threading libraries.