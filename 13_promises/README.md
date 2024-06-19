# Promise
A Promise is an object representing the eventual completion or failure of an asynchronous operation. It allows you to write asynchronous code in a more synchronous and manageable way.

### Basic Structure of a Promise
A Promise can be in one of three states:

* Pending: The initial state, neither fulfilled nor rejected.
* Fulfilled: The operation completed successfully.
* Rejected: The operation failed.

***Creating a Promise***

```ts
const myPromise = new Promise<number>((resolve, reject) => {
    const success = true; // Simulate success or failure
    if (success) {
        resolve(42); // Fulfilled with value 42
    } else {
        reject(new Error("Something went wrong!")); // Rejected with error
    }
});
```

***Consuming a Promise***

```ts
myPromise
    .then(value => {
        console.log("Promise fulfilled with value:", value); // Output: Promise fulfilled with value: 42
    })
    .catch(error => {
        console.error("Promise rejected with error:", error);
    });
```

# Promise.all
Promise.all is a method that takes an array of promises and returns a single promise. This promise resolves when all of the promises in the array have resolved, or rejects if any of the promises in the array reject.

```ts
const promise1 = Promise.resolve(1);
const promise2 = Promise.resolve(2);
const promise3 = Promise.resolve(3);

Promise.all([promise1, promise2, promise3])
    .then(values => {
        console.log(values); // Output: [1, 2, 3]
    })
    .catch(error => {
        console.error("One of the promises rejected:", error);
    });
```

#### Explanation
- If all promises resolve, Promise.all resolves with an array of their values.
- If any promise rejects, Promise.all immediately rejects with the reason of the first promise that rejected.

# Promise.race
Promise.race is a method that takes an array of promises and returns a single promise. This promise resolves or rejects as soon as one of the promises in the array resolves or rejects.

```ts
const promise1 = new Promise((resolve) => setTimeout(resolve, 500, 'one'));
const promise2 = new Promise((resolve) => setTimeout(resolve, 100, 'two'));

Promise.race([promise1, promise2])
    .then(value => {
        console.log(value); // Output: "two" (promise2 resolves first)
    })
    .catch(error => {
        console.error("One of the promises rejected:", error);
    });
```

#### Explanation
- Promise.race returns a promise that resolves or rejects as soon as one of the promises in the array resolves or rejects.
- In the example above, promise2 resolves first after 100ms, so the output is "two".

### Conclusion
- Promises: Provide a clean way to handle asynchronous operations.
- Promise.all: Waits for all promises to resolve or any to reject.
- Promise.race: Resolves or rejects as soon as one of the promises resolves or rejects.