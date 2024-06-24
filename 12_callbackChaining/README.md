# Callback Chaining
Callback chaining is a technique to handle multiple asynchronous operations in a sequence without nesting callbacks within each other, thus avoiding "callback hell".

## Using Promises

```ts
function fetchUser(userId: number): Promise<{ id: number; name: string }> {
    return new Promise((resolve) => {
        setTimeout(() => resolve({ id: userId, name: "Alice" }), 1000);
    });
}

function fetchUserDetails(user: { id: number; name: string }): Promise<{ id: number; name: string; age: number }> {
    return new Promise((resolve) => {
        setTimeout(() => resolve({ ...user, age: 30 }), 1000);
    });
}

fetchUser(1)
    .then(user => {
        console.log("User:", user);
        return fetchUserDetails(user);
    })
    .then(details => {
        console.log("User Details:", details);
    })
    .catch(error => {
        console.error("Error:", error);
    });
```

#### Explanation:

- fetchUser: Returns a promise that resolves with user data.
- fetchUserDetails: Returns a promise that resolves with user details.
- Chaining: Use `.then` to handle each step in sequence, and `.catch` for error handling.

## Using Async/Await

```ts
async function getUserDetails(userId: number) {
    try {
        const user = await fetchUser(userId);
        console.log("User:", user);
        const details = await fetchUserDetails(user);
        console.log("User Details:", details);
    } catch (error) {
        console.error("Error:", error);
    }
}

getUserDetails(1);
```

#### Explanation:

- async Function: Allows using `await` to pause execution until promises resolve.
- await: Retrieves results from promises sequentially.
- Error Handling: Managed with `try...catch`.

### Summary
- Callback Chaining: Sequential execution of asynchronous operations.
- Promises: Use `.then` and `.catch` to chain operations.
- Async/Await: Synchronous-like syntax for handling promises, improving readability.





