# Async/Await
Async/Await is a modern syntax for handling asynchronous operations. It is built on top of Promises and allows you to write asynchronous code that looks and behaves like synchronous code, making it more readable and easier to manage.

- `async` Keyword: Declares an asynchronous function. It automatically *returns a promise*.
- `await` Keyword: Pauses the execution of an async function and waits for the promise to resolve or reject.

```ts
async function getData() {
    try {
        const data = await fetchData('https://api.example.com');
        console.log(data);
    } catch (error) {
        console.error("Error fetching data:", error);
    }
}

getData();
```
*Error handling in async functions is done using `try...catch` blocks.*

## Parallel Async Operations
To run asynchronous operations in parallel, use Promise.all.

```ts
async function getMultipleData() {
    try {
        const [data1, data2] = await Promise.all([
            fetchData('https://api.example.com/data1'),
            fetchData('https://api.example.com/data2')
        ]);
        console.log("Data 1:", data1);
        console.log("Data 2:", data2);
    } catch (error) {
        console.error("Error:", error);
    }
}

getMultipleData();
```
#### Explanation
- Promise.all: Runs both fetchData calls in parallel.
- await: Waits for both promises to resolve and returns an array of results.