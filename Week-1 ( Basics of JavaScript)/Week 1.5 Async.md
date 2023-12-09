# Async functions vs sync functions, real use of callbacks JS Browser architecture Promises Async await

## Async functions vs sync functions

### What does synchronous mean?
- Together, one after the other, sequential Only one thing is happening at a time

###  What does asynchronous mean?
- Opposite of synchronous Happens in parts Multiple things are context switching with each other

| Aspect                   | Synchronous Functions                                | Asynchronous Functions                                |
|--------------------------|------------------------------------------------------|--------------------------------------------------------|
| Execution                | Blocks execution until completion                    | Does not block execution, allows other code to run      |
| Syntax                   | Typically straightforward, linear                    | Involves keywords like `async`, `await`, and Promises  |
| Usage                    | Commonly used for simple, sequential tasks           | Ideal for I/O-bound or time-consuming operations        |
| Performance              | Can lead to blocking behavior, potentially slower    | Efficient for handling multiple tasks concurrently     |
| Error Handling           | Relatively simpler, uses try-catch blocks            | Requires careful handling of Promises and error chains |
| Callbacks/Promises       | Not inherently reliant on Promises or callbacks      | Built on top of Promises, utilizes async/await syntax  |
| Control Flow             | Follows a linear control flow                         | Allows non-linear, event-driven control flow            |
| Examples                 | Basic arithmetic operations, simple data processing  | Fetching data from APIs, reading files asynchronously  |

Synchronous functions execute one operation at a time in a sequential manner, which means the program waits for each function to finish before moving to the next one. This might lead to blocking behavior, especially in situations where operations take a significant amount of time.

Asynchronous functions, on the other hand, allow the program to continue executing other tasks while waiting for asynchronous operations (like reading files, making API calls) to complete. This is achieved using concepts like Promises and the `async` and `await` keywords. As a result, they are more suitable for handling operations that might take time without halting the entire program.

#Async functions vs sync functions
- Lets build some intuition
Human brain and body is single threaded
1. We can only do one thing at a time
2. But we can context switch b/w tasks, or we can delegate tasks to other people

You have 4 tasks -
1. Boil water
2. Cut vegetables
3. Cut maggi packet
4. Get ketchup from the shop nearby
How would you do this? Synchronously or Asynchronously

-  Even if you are single threaded (brain can do only one thing at a time), you can do things parallely by Delegating
- You can also context switch between tasks if need be (the net time to do both the things would still be the same) Net amount of time take to do a task can be decreased by doing these two things (delegating and context switching)
# How does JS do the same? Can JS delegate? Can JS context switch?
In JavaScript, asynchronous behavior is achieved through mechanisms like event loop, callbacks, Promises, and async/await, allowing for delegation and context switching.

1. **Event Loop:** The event loop is the core mechanism that allows JavaScript to handle asynchronous operations. It continuously checks the call stack and the task queue. When the call stack is empty, the event loop takes functions from the task queue and pushes them onto the call stack for execution.

2. **Callbacks:** Callbacks are functions passed as arguments to other functions. They are commonly used in asynchronous operations to execute code once an asynchronous task completes. For example:

    ```javascript
    setTimeout(function() {
        console.log("This executes after 2 seconds");
    }, 2000);
    ```

3. **Promises:** Promises provide a more structured way to work with asynchronous code. They represent a value that might be available now, in the future, or never. Promises have methods like `.then()` to handle success and `.catch()` to handle errors.

    ```javascript
    function fetchData() {
        return new Promise((resolve, reject) => {
            // Simulating an API call
            setTimeout(() => {
                if (/* data is successfully fetched */) {
                    resolve('Data fetched successfully');
                } else {
                    reject('Error fetching data');
                }
            }, 2000);
        });
    }

    fetchData()
        .then(result => {
            console.log(result);
        })
        .catch(error => {
            console.error(error);
        });
    ```

4. **Async/Await:** Async functions are a cleaner way to write asynchronous code in JavaScript, using the `async` and `await` keywords. Async functions return Promises implicitly and allow writing code that looks synchronous but behaves asynchronously.

    ```javascript
    async function fetchData() {
        try {
            const response = await fetch('https://api.example.com/data');
            const data = await response.json();
            console.log(data);
        } catch (error) {
            console.error(error);
        }
    }

    fetchData();
    ```

JavaScript achieves delegation and context switching through these asynchronous mechanisms. When an asynchronous operation is encountered, rather than blocking the execution, JavaScript delegates the task to another part of the program (like the browser's API for handling network requests). When the asynchronous operation completes, it returns to the event loop, which then puts the corresponding callback or Promise resolution into the execution stack for further processing. This allows JavaScript to effectively handle multiple tasks without blocking.

- setTimeout
- fs.readFile - to read a file from your filesystem
- Fetch - to fetch some data from an API endpoint