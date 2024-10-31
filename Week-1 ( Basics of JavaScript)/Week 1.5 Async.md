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

## Real Use of Callbacks

Callbacks are functions passed as arguments to other functions and executed after some kind of event or operation has completed. They are widely used in asynchronous programming to manage tasks that do not finish immediately, allowing JavaScript to handle long-running operations without blocking the execution of other code.

### Key Concepts of Callbacks

1. **Function as a First-Class Citizen**: In JavaScript, functions are "first-class citizens," meaning they can be treated like any other variable. You can pass functions as arguments, return them from other functions, and assign them to variables.

2. **Synchronous vs. Asynchronous Callbacks**:
   - **Synchronous Callbacks**: Executed immediately, as part of a regular function execution. These callbacks are used when you want to perform operations in a specific order without delays.
   - **Asynchronous Callbacks**: Executed after a specific event or operation completes, often without blocking other code from executing. These are typical in situations like network requests, timers, or reading files.

3. **How Callbacks Work**:
   - A callback function is passed to another function.
   - The main function executes and, once it reaches the callback point, invokes the callback function.
   - In asynchronous cases, the main function might continue executing without waiting for the callback.

### Examples of Callbacks in JavaScript

#### 1. Simple Synchronous Callback

Here's a synchronous example where a function calls another function after performing an operation:

```javascript
function greet(name) {
  console.log(`Hello, ${name}!`);
}

function welcome() {
  console.log("Welcome to our website!");
}

function greetAndWelcome(userName) {
  greet(userName); // Calling the greet function inside greetAndWelcome
  welcome(); // Calling the welcome function inside greetAndWelcome
}

// Calling the greetAndWelcome function
greetAndWelcome("Alice");
```

In this case:
- `greetAndWelcome` is a function that calls both `greet` and `welcome`. When `greetAndWelcome("Alice")` is called, it invokes the `greet` function with the provided name (`"Alice"`) and then calls the `welcome` function to display a welcome message.

#### 2. Asynchronous Callback with `setTimeout`

Here’s an example using an asynchronous callback with `setTimeout`, which delays execution of the callback function:

```javascript
function displayMessage() {
  console.log("This message is displayed after 2 seconds.");
}

setTimeout(displayMessage, 2000);  // Executes displayMessage after 2 seconds
```

- `setTimeout` is passed `displayMessage` as a callback function.
- `setTimeout` waits 2 seconds and then invokes `displayMessage`.

#### 3. Asynchronous Callback in HTTP Requests (Example with Fetch API)

Using callbacks with HTTP requests is common in JavaScript for handling data after a request completes:

```javascript
function fetchData(callback) {
  fetch("https://jsonplaceholder.typicode.com/posts/1")
    .then(response => response.json())
    .then(data => callback(data))
    .catch(error => console.log("Error:", error));
}

function displayData(data) {
  console.log("Data fetched:", data);
}

// Example Usage
fetchData(displayData);
```

Here:
- `fetchData` initiates an HTTP request and calls `displayData` (passed as a callback) with the data once the request is successful.

### Callback Challenges: Callback Hell

As you nest multiple callbacks, readability and maintainability can suffer. This phenomenon is often referred to as **callback hell**:

```javascript
function firstTask(callback) {
  setTimeout(() => {
    console.log("First task done.");
    callback();
  }, 1000);
}

function secondTask(callback) {
  setTimeout(() => {
    console.log("Second task done.");
    callback();
  }, 1000);
}

function thirdTask() {
  setTimeout(() => {
    console.log("Third task done.");
  }, 1000);
}

// Nested callbacks
firstTask(() => {
  secondTask(() => {
    thirdTask();
  });
});
```

In such cases, managing nested callbacks becomes difficult, and errors are hard to debug.

### Solutions to Callback Hell: Promises and Async/Await

To handle asynchronous code more cleanly, JavaScript introduced **Promises** and later **async/await** syntax, which make chaining asynchronous actions easier and code more readable.

#### Using Promises

```javascript
function firstTask() {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log("First task done.");
      resolve();
    }, 1000);
  });
}

function secondTask() {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log("Second task done.");
      resolve();
    }, 1000);
  });
}

function thirdTask() {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log("Third task done.");
      resolve();
    }, 1000);
  });
}

// Chaining Promises
firstTask()
  .then(() => secondTask())
  .then(() => thirdTask());
```

#### Using Async/Await

```javascript
async function executeTasks() {
  await firstTask();
  await secondTask();
  await thirdTask();
}

executeTasks();
```

With **async/await**, the code becomes simpler, looks synchronous, and avoids the deep nesting of callbacks.

## JS Browser Architecture

JavaScript is single-threaded, meaning it has only one call stack and one memory heap. This single-threaded behavior in JavaScript has a significant impact on how code is executed within the language.

### Characteristics of Single-Threaded Nature in JavaScript:

1. **Call Stack:** JavaScript utilizes a single call stack, known as the "event loop," to handle function execution. It manages the order of function calls and their respective execution contexts.

2. **Blocking Operations:** If a function takes longer to execute, such as performing I/O operations or computations, it can block the execution of other code in the stack, causing delays or freezing the user interface in the case of browser-based JavaScript.

3. **Asynchronous Operations:** To mitigate blocking issues, JavaScript utilizes asynchronous programming, allowing certain operations (like fetching data from a server, reading files, etc.) to be executed without blocking the main thread. This is typically achieved using callbacks, promises, async/await, or event-driven programming.

4. **Event Loop:** JavaScript's event loop manages the execution of asynchronous code by continuously checking the call stack and the message queue. When the call stack is empty, it picks tasks/events from the queue and executes them, allowing non-blocking operations to be processed.

5. **Concurrency:** While JavaScript is single-threaded, it can achieve concurrent behavior through asynchronous operations. It handles concurrent operations by delegating I/O tasks to browser APIs or runtime environments (like Node.js) that execute these operations independently and notify JavaScript through callback functions when they are completed.

### Benefits and Challenges:

**Benefits:**
- Simplicity: Easier to write and reason about code due to its single-threaded nature.
- Predictability: Execution order is more straightforward, which can simplify debugging.
- Event-driven: Enables responsive and non-blocking I/O operations.

**Challenges:**
- Blocking Code: Long-running operations can block the main thread, leading to performance issues and unresponsiveness.
- Synchronization: Dealing with shared resources in a single-threaded environment requires careful management to prevent race conditions and maintain data integrity.

## Promises

Promises are syntactical sugar that make this code slightly more readable

How can we create an asynchronous function of our own?
It is just a wrapper on top of another async function, 
which is fine. 
Usually all async functions you will write will be on top of 
JS provided async functions like setTimeout or fs.readFile

You can create your own asynchronous function in JavaScript using the `async` and `await` keywords. These keywords were introduced in ECMAScript 2017 (ES8) and provide a more straightforward way to work with asynchronous code by making it look synchronous.

Here's an example of creating an asynchronous function:

```javascript
// Using async function to create an asynchronous function
async function myAsyncFunction() {
  // Asynchronous task (e.g., fetching data from an API, reading a file, etc.)
  // This can be a Promise-based operation or function that returns a Promise

  // Simulating a delay with setTimeout (asynchronous operation)
  const result = await new Promise((resolve) => {
    setTimeout(() => {
      resolve('Async operation completed');
    }, 2000); // Resolves after 2 seconds
  });

  // The await keyword pauses the execution until the promise is resolved
  return result;
}

// Using the asynchronous function
async function executeAsyncFunction() {
  try {
    const asyncResult = await myAsyncFunction(); // Wait for myAsyncFunction to complete
    console.log(asyncResult); // Output: 'Async operation completed'
    // You can perform further operations after getting the result
  } catch (error) {
    console.error(error); // Handle any errors that might occur during execution
  }
}

// Calling the function that uses the asynchronous function
executeAsyncFunction();
```

Explanation:

- The `async` keyword before the function declaration defines it as an asynchronous function, allowing the use of `await` within it.
- Inside the `myAsyncFunction`, the `await` keyword is used to pause the execution until the asynchronous operation (in this case, a `setTimeout` wrapped in a Promise) is completed.
- `await` can only be used within an `async` function and is used to wait for a Promise to resolve. It makes asynchronous code look and behave more like synchronous code.
- You can then use `try...catch` blocks to handle both resolved values and errors from asynchronous operations in a synchronous-style manner.

What even is a promise? 
It is just a class that makes callbacks and async functions slightly more readable.

## Importance of Understanding Asynchronous Programming

Understanding asynchronous programming in JavaScript is crucial for building scalable and efficient systems. Here are some key reasons why:

1. **Non-Blocking I/O Operations**: Asynchronous programming allows you to perform I/O operations (like reading files, making network requests) without blocking the main thread. This ensures that your application remains responsive and can handle multiple tasks concurrently.

2. **Improved Performance**: By leveraging asynchronous operations, you can improve the performance of your application. Tasks that would otherwise block the main thread can be executed in the background, allowing other tasks to proceed without delay.

3. **Scalability**: Asynchronous programming enables your application to handle a large number of concurrent connections efficiently. This is particularly important for web servers and real-time applications where multiple users may be interacting with the system simultaneously.

4. **User Experience**: In client-side applications, asynchronous programming ensures a smooth and responsive user experience. Long-running tasks can be executed without freezing the user interface, providing a seamless interaction for users.

5. **Resource Utilization**: Asynchronous programming allows for better utilization of system resources. By delegating tasks to background processes or external services, you can optimize the use of CPU, memory, and network resources.

6. **Error Handling**: Asynchronous programming provides mechanisms for handling errors and exceptions in a structured manner. Promises and async/await syntax make it easier to manage and propagate errors, ensuring robust and reliable code.

7. **Modularity and Reusability**: Asynchronous functions and Promises promote modular and reusable code. You can encapsulate asynchronous operations into separate functions or modules, making your codebase more maintainable and easier to understand.

8. **Compatibility with Modern Frameworks**: Many modern JavaScript frameworks and libraries, such as React, Angular, and Node.js, heavily rely on asynchronous programming. Understanding asynchronous concepts is essential for effectively working with these frameworks and leveraging their full potential.

By mastering asynchronous programming in JavaScript, you can build scalable, performant, and user-friendly applications that can handle complex tasks and provide a seamless experience for users.

