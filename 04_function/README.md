# Callback Functions

* A callback function is a function that is passed as an argument to another function, and it is executed after some kind of event or operation has occurred.

* When you pass a function as an argument to another function, you are passing a reference to the function. The receiving function can then call this reference at the appropriate time.

```ts
function greet(name: string) {
    console.log(`Hello, ${name}`);
}

function processUserInput(callback: (name: string) => void) {
    let name = "John Doe"; // Simulating user input
    callback(name);
}

processUserInput(greet); // Output: Hello, John Doe
```

* Greet is a function that takes a string and logs a greeting message.
* ProcessUserInput is a function that takes another function (callback) as an argument and calls it with a simulated user input.
* Greet is passed as the callback to processUserInput and is called with the name "John Doe".