

# Week 1.2 | JS Foundation 🚀

## Why Language 🔍

1. Languages are used to write applications
2. Developers write high level code in these languages
3. Every language has a **Complier** which converts the developer code into 01

In technical terms, a programming language is a formal set of instructions, rules, and syntax used to create software, applications, websites, and various technological solutions. It provides a structured way for programmers to communicate with computers, enabling them to write code that can be understood and executed by machines.

### Key aspects of programming languages include: 💻

1. **Syntax and Semantics:** Programming languages have specific rules (syntax) and meanings (semantics) governing how code should be written and interpreted. Syntax refers to the grammar and structure of the language, while semantics define the meaning and behavior of the code.

2. **Abstraction:** Languages offer different levels of abstraction, allowing programmers to work at varying degrees of complexity. Higher-level languages abstract away low-level details, making it easier to write code, while lower-level languages provide more control and direct interaction with hardware.

3. **Expressiveness:** Programming languages vary in their expressiveness, i.e., the ease with which complex operations or concepts can be conveyed and executed in code. Some languages are concise and allow for efficient code writing, while others prioritize readability and explicitness.

4. **Execution:** Once written, code in a programming language needs to be translated or compiled into machine-readable instructions that the computer's processor can understand and execute.

5. **Paradigms:** Programming languages often follow specific programming paradigms, such as procedural, object-oriented, functional, or declarative approaches. These paradigms define the style and methodology used to solve problems and structure code.

6. **Tooling and Ecosystem:** Each programming language typically has its set of tools, libraries, and frameworks that assist developers in writing code efficiently and solving particular types of problems.

Programming languages serve as a bridge between human understanding and machine execution. They empower developers to create diverse software solutions by providing a standardized way to communicate instructions to computers, enabling the development of everything from simple scripts to complex applications and systems.

### What is Compiler 🛠️

A compiler is a specialized program that translates source code written in a high-level programming language into machine code or executable code that a computer can understand and execute directly.

- Step 1:- write code ✏️
- Step 2:- Complile code 🔄
- Step 3:- Run the code (put it in ram) ▶️

Here are some well-known examples of compilers:

1. **GCC (GNU Compiler Collection)** - A popular compiler for languages like C, C++, Objective-C, Fortran, and others. It is widely used in Unix-based systems and is part of the GNU Project.

2. **Clang** - An alternative to GCC, Clang is a compiler for C, C++, and Objective-C languages and is part of the LLVM project. It's known for providing fast compilation times and excellent diagnostics.

3. **Microsoft Visual C++ Compiler** - A compiler provided by Microsoft for C and C++ programming as part of Visual Studio. It is commonly used on Windows platforms.

4. **Java Compiler (javac)** - This compiler is part of the Java Development Kit (JDK) and compiles Java source code into bytecode, which can be executed on the Java Virtual Machine (JVM).

5. **Intel C++ Compiler (ICC)** - A compiler optimized for Intel processors, often used in high-performance computing due to its optimizations and compatibility with Intel hardware.

6. **Swift Compiler** - A compiler for the Swift programming language, used primarily for iOS and macOS app development. It is integrated into Apple's Xcode IDE.

7. **Kotlin Compiler** - Compiles Kotlin code to Java bytecode, which can run on the JVM, or to JavaScript and native binaries for cross-platform applications.

8. **PyInstaller and Nuitka (for Python)** - These aren't traditional compilers in the sense of creating machine code, but they allow Python code to be packaged into standalone executables.

### What is Interpreter 🔍

Interpreted languages are programming languages where the source code is directly executed line-by-line by an interpreter without the need for a separate compilation step. Instead of compiling the entire code into machine code before execution (as in compiled languages), an interpreter reads and executes the code statement by statement in real-time.

### Compiled vs Interpreted Languages 📊

| Aspect                 | Compiled Languages                           | Interpreted Languages                         |
|------------------------|----------------------------------------------|----------------------------------------------|
| **Process**            | First need to compile, then need to run      | Usually go line by line                      |
| **Error Handling**     | Usually don't compile if there is an error in the code | Can run partially if the error comes later  |
| **Execution Process**  | Entire source code is compiled into machine code before execution | Source code is read line-by-line and translated into machine code in real-time |
| **Output**             | Produces standalone executable files or libraries | Does not produce standalone executable files; code executed through an interpreter |
| **Performance**        | Generally faster execution since code is pre-compiled into machine code | May have slightly slower execution due to on-the-fly translation |
| **Portability**        | Executable files might be platform-specific and might require recompilation for different systems | More portable as the interpreter can run on various platforms without recompilation |
| **Debugging**          | Errors are often detected during compilation and may be easier to pinpoint | Errors might be detected during runtime and might be harder to pinpoint |
| **Development Speed**  | Longer compilation times, but potentially faster execution | Shorter development cycles as changes in code can be executed immediately |
| **Examples**           | C, C++, Rust, Go, Swift                     | Python, JavaScript, Ruby, PHP, Perl        |

### Why JavaScript better than other languages 🌟

- Browsers can only understand HTML/CSS/JS (not technically true) Thanks to Node.Js, Javascript can also be used for "Backend Development"

### Static vs Dynamic Languages 📋

| Aspect                            | Static Languages                      | Dynamic Languages                    |
|-----------------------------------|---------------------------------------|--------------------------------------|
| **Type Checking**                 | Type checking is done at compile time | Type checking occurs at runtime      |
| **Variable Declaration**          | Requires explicit variable declaration with types | Variables are often declared without specifying types |
| **Compilation**                   | Compiled before runtime               | Interpreted or compiled at runtime   |
| **Error Detection**               | Early error detection during compilation | Errors can occur during runtime      |
| **Performance**                   | Often faster due to optimizations performed during compilation | Generally slower due to runtime type checks and flexibility |
| **Memory Usage**                  | Typically more memory-efficient as types are known in advance | May use more memory due to dynamic typing |
| **Flexibility**                   | Less flexible as types need to be specified | More flexible as types can be changed during runtime |
| **Examples**                      | C, C++, Java, TypeScript, etc.       | JavaScript, Python, Ruby, PHP, etc.  |

JavaScript is known for its single-threaded nature, meaning it has only one call stack and one memory heap. This single-threaded behavior in JavaScript has a significant impact on how code is executed within the language.

### Characteristics of Single-Threaded Nature in JavaScript: 🧵

1. **Call Stack:** JavaScript utilizes a single call stack, known as the "event loop," to handle function execution. It manages the order of function calls and their respective execution contexts.

2. **Blocking Operations:** If a function takes longer to execute, such as performing I/O operations or computations, it can block the execution of other code in the stack, causing delays or freezing the user interface in the case of browser-based JavaScript.

3. **Asynchronous Operations:** To mitigate blocking issues, JavaScript utilizes asynchronous programming, allowing certain operations (like fetching data from a server, reading files, etc.) to be executed without blocking the main thread. This is typically achieved using callbacks, promises, async/await, or event-driven programming.

4. **Event Loop:** JavaScript's event loop manages the execution of asynchronous code by continuously checking the call stack and the message queue. When the call stack is empty, it picks tasks/events from the queue and executes them, allowing non-blocking operations to be processed.

5. **Concurrency:** While JavaScript is single-threaded, it can achieve concurrent behavior through asynchronous operations. It handles concurrent operations by delegating I/O tasks to browser APIs or runtime environments (like Node.js) that execute these operations independently and notify JavaScript through callback functions when they are completed.

### Benefits and Challenges: ⚖️

**Benefits:**
- 👍 **Simplicity:** Easier to write and reason about code due to its single-threaded nature.
- 👍 **Predictability:** Execution order is more straightforward, which can simplify debugging.
- 👍 **Event-driven:** Enables responsive and non-blocking I/O operations.

**Challenges:**
- 👎 **Blocking Code:** Long-running operations can block the main thread, leading to performance issues and unresponsiveness.
- 👎 **Synchronization:** Dealing with shared resources in a single-threaded environment requires careful management to prevent race conditions and maintain data integrity.

> ⚠️ **Note:** JS can only one of these at a time It is single threaded. This is why it is considered to be a bad language for scalable systems. There is a way to make it use all cores of your machine.

## Simple Primitives 🧩

### Variable Declarations: `var`, `let`, `const` 📦

#### `var`:
- Declares a variable globally scoped or function scoped.
- Variables declared with `var` can be re-declared and updated.
- They are hoisted to the top of their scope during execution.

#### `let`:
- Introduces block-scoped variables.
- Allows the variable to be reassigned but not re-declared in the same scope.
- Does not get hoisted to the top of the scope, unlike `var`.

#### `const`:
- Declares a constant block-scoped variable.
- The value of a `const` cannot be reassigned once it is initialized.
- It does not allow re-declaration or reassignment.

### Data Types: Strings, Numbers, Booleans 🔢

#### Strings:
- Represents textual data enclosed in single or double quotes.
- Example: `let greeting = 'Hello';`

#### Numbers:
- Represents numeric values, including integers and floating-point numbers.
- Example: `let count = 10;`

#### Booleans:
- Represents a logical value, either `true` or `false`.
- Often used in conditional statements.
- Example: `let isTrue = true;`

### Control Flow: `if`/`else` Statements and `for` Loops 🔄

#### `if`/`else` Statements:
- Used for conditional execution based on a condition's evaluation.
- Syntax:
  ```javascript
  if (condition) {
    // Code to execute if condition is true
  } else {
    // Code to execute if condition is false
  }
  ```

#### `for` Loops:
- Used for iterating over a block of code multiple times.
- Syntax:
  ```javascript
  for (initialization; condition; iteration) {
    // Code block to be executed
  }
  ```
  - `initialization`: Executes once before the loop starts.
  - `condition`: Checked before every iteration. If false, the loop stops.
  - `iteration`: Executed at the end of each iteration.

### Example: 💡

```javascript
// Variable declarations
let name = 'Alice';
var age = 25;
const isStudent = true;

// Conditional statement
if (age >= 18) {
  console.log(`${name} is an adult.`);
} else {
  console.log(`${name} is a minor.`);
}

// For loop example
for (let i = 0; i < 5; i++) {
  console.log(i); // Outputs numbers from 0 to 4
}
```

These JavaScript fundamentals - variable declarations, data types, conditional statements (`if`/`else`), and loops (`for` loops) - are foundational concepts used extensively in JavaScript programming to create logic, manipulate data, and control the flow of execution within programs.

## JavaScript Code Examples 📝

### 1. Greet a Person Given Their First and Last Name 👋

```javascript
function greetPerson(firstName, lastName) {
    console.log(`Hello, ${firstName} ${lastName}!`);
}

// Example Usage
greetPerson("John", "Doe");
```

### 2. Greet a Person Based on Their Gender 👨‍👩‍👧

```javascript
function greetByGender(name, gender) {
    if (gender.toLowerCase() === "male") {
        console.log(`Hello Mr. ${name}!`);
    } else if (gender.toLowerCase() === "female") {
        console.log(`Hello Ms. ${name}!`);
    } else {
        console.log(`Hello ${name}!`);
    }
}

// Example Usage
greetByGender("Alex", "male");
greetByGender("Sarah", "female");
greetByGender("Taylor", "other");
```

### 3. Program that Counts from 0 to 1000 and Prints Each Number 🔢

```javascript
for (let i = 0; i <= 1000; i++) {
    console.log(i);
}
```

## Array Manipulation Examples 📊

### 1. Program to Print All Even Numbers in an Array 🔢

```javascript
function printEvenNumbers(arr) {
    arr.forEach(num => {
        if (num % 2 === 0) {
            console.log(num);
        }
    });
}

// Example Usage
printEvenNumbers([11, 22, 33, 44, 55, 66, 77, 88, 99, 100]);
```

### 2. Program to Print the Biggest Number in an Array 📈

```javascript
function findBiggestNumber(arr) {
    let max = arr[0];
    arr.forEach(num => {
        if (num > max) {
            max = num;
        }
    });
    console.log(`The biggest number is: ${max}`);
}

// Example Usage
findBiggestNumber([3, 71, 27, 91, 12, 52, 15, 43]);
```

### 3. Program to Print First Names of All Male People in a Complex Object 👨

```javascript
const people = [
    { firstName: "Rajesh", lastName: "Patel", gender: "male" },
    { firstName: "Anita", lastName: "Desai", gender: "female" },
    { firstName: "Vikram", lastName: "Singh", gender: "male" },
    { firstName: "Priya", lastName: "Rao", gender: "female" }
];

function printMaleFirstNames(peopleArray) {
    peopleArray.forEach(person => {
        if (person.gender === "male") {
            console.log(person.firstName);
        }
    });
}

// Example Usage
printMaleFirstNames(people);
```

### 4. Program to Reverse All Elements of an Array ↩️

```javascript
function reverseArray(arr) {
    const reversedArr = arr.reverse();
    console.log(reversedArr);
}

// Example Usage
reverseArray(["Ajay", "Vijay", "Sunita", "Rekha", "Pooja", "Ramesh", "Sneha"]);
```

## Function Examples 🧩

### 1. Function to Find the Sum of Two Numbers ➕

```javascript
function findSum(num1, num2) {
    return num1 + num2;
}

// Example Usage
const sum = findSum(10, 15); // 25
```

### 2. Function to Display the Sum in a Pretty Format 🎨

```javascript
function displaySumPretty(sum) {
    console.log(`The sum of the two numbers is: ${sum}`);
}

// Example Usage
displaySumPretty(sum); // "The sum of the two numbers is: 25"
```

### 3. Function to Print the Sum in Passive Tense 📢

```javascript
function displaySumPassive(sum) {
    console.log(`The result has been calculated as: ${sum}`);
}

// Example Usage
displaySumPassive(sum); // "The result has been calculated as: 25"
```

### Full Program 🔄

```javascript
function findSum(num1, num2) {
    return num1 + num2;
}

function displaySumPretty(sum) {
    console.log(`The sum of the two numbers is: ${sum}`);
}

function displaySumPassive(sum) {
    console.log(`The result has been calculated as: ${sum}`);
}

// Example Usage
const sum = findSum(10, 15);
displaySumPretty(sum);
displaySumPassive(sum);
```

## System Monitoring Tools 🖥️

`top` and `htop` are popular command-line tools for monitoring system performance, particularly in Unix-like operating systems such as Linux and macOS. Both tools provide real-time information about system processes, CPU, memory usage, and more.

### 1. `top` 📊

`top` is a standard command-line utility that provides a dynamic view of system processes. By default, it shows processes sorted by CPU usage, with the most CPU-intensive processes listed at the top.

#### Key Features of `top` 🔑
- **Real-Time System Monitoring**: Displays CPU and memory usage, load averages, uptime, and swap usage.
- **Process Monitoring**: Lists processes with details like PID (process ID), user, priority, memory usage, and CPU percentage.
- **Process Management**: Allows you to kill processes by entering the process ID (PID) directly from the interface.
- **Customizable**: You can change the sort order (by memory usage, PID, etc.), and adjust the update frequency by modifying the settings within the tool.

#### Common Commands in `top` ⌨️
- **`q`** - Quit the `top` interface.
- **`k`** - Kill a process by entering its PID.
- **`h`** - View help information for more commands.
- **`M`** - Sort processes by memory usage.
- **`P`** - Sort processes by CPU usage (default).

#### Limitations of `top` ⚠️
While `top` provides essential data, its interface is somewhat limited and lacks the modern interactive features that some users prefer. This is where `htop` comes in as a more feature-rich alternative.

### 2. `htop` 📈

`htop` is an enhanced, interactive version of `top`. It offers a more user-friendly interface, often with color-coding and an easier-to-navigate layout.

#### Key Features of `htop` 🔑
- **Visual Interface**: `htop` uses colors to represent different types of system usage, making it more visually appealing and easier to read than `top`.
- **Easy Process Navigation**: You can scroll through the list of processes both vertically and horizontally, which is useful when examining detailed information.
- **Customizable Display**: Allows you to change what information is shown, choose sorting options, and configure the display to fit your preferences.
- **Process Management**: Similar to `top`, but `htop` makes it easier to kill, renice, or search for processes interactively.
- **Extended Information**: `htop` provides additional details, such as real-time graphical bars for CPU, memory, and swap usage.

#### Common Commands in `htop` ⌨️
- **`F3`** - Search for a specific process by name.
- **`F5`** - Display processes in a tree structure to view parent-child relationships.
- **`F6`** - Sort processes by a chosen field, such as CPU or memory usage.
- **`F9`** - Kill a selected process.
- **`F10`** - Quit `htop`.

#### Advantages of `htop` over `top` 👍
- More interactive and visually intuitive, making it easier for beginners and experts alike.
- Supports mouse input, so you can scroll, kill processes, and interact with elements directly.
- Displays more detailed information on memory usage, including buffers and cached memory, which `top` does not always show by default.

#### Limitations of `htop` ⚠️
While `htop` provides a lot of functionality, it is not available by default on all systems and may need to be installed. Additionally, it uses slightly more system resources than `top`.

### Summary 📋
- **`top`** is a standard, lightweight monitoring tool available by default on most Unix-like systems. It's simple and effective for quick process monitoring.
- **`htop`** is an advanced, visually enhanced alternative to `top`, with a customizable and interactive interface suitable for more in-depth monitoring.

Both tools are valuable for system administrators, developers, and power users looking to monitor and manage system performance efficiently.

## Synchronous vs Asynchronous JavaScript ⏱️

| Feature                         | Synchronous                                   | Asynchronous                                      |
|---------------------------------|-----------------------------------------------|---------------------------------------------------|
| **Definition**                  | Executes code sequentially, one line after the other. Each line waits for the previous line to complete. | Executes code without waiting; can run multiple tasks concurrently, allowing some tasks to continue while waiting for others. |
| **Blocking Behavior**           | Blocking - each task waits for the previous task to finish before starting. | Non-blocking - tasks can start and continue even if previous tasks haven't completed. |
| **Execution Order**             | Deterministic; the code is executed in the order written. | Non-deterministic; the order of execution depends on task completion. |
| **Examples**                    | Basic arithmetic, string operations, and loops. | SetTimeout, HTTP requests (fetch), reading files with Promises or async functions. |
| **Performance Impact**          | Can slow down the application, especially with long-running tasks, as it blocks other code from running. | Improves application performance by freeing up resources while waiting for tasks to complete. |
| **Coding Style**                | Simple and easy to read, as it follows a straightforward, top-down approach. | Requires callbacks, Promises, or async/await syntax to handle asynchronous operations, which can be more complex to write and understand. |
| **Error Handling**              | Errors are immediate and stop further execution if not caught. | Errors are often handled in callbacks, `.catch` for Promises, or with `try/catch` in async/await functions. |
| **Use Cases**                   | When operations are short and need to execute in order, like mathematical calculations or simple functions. | When tasks involve time delays or waiting, such as API calls, file I/O, or database operations. |

In JavaScript, the **Event Loop** and **Callback Queue** help manage asynchronous operations, making it a powerful language for both synchronous and asynchronous code execution.

## Callbacks in JavaScript 📞

In JavaScript, a **callback** is a function passed as an argument to another function and executed after some kind of event or operation has completed. Callbacks are widely used in asynchronous programming to manage tasks that do not finish immediately, allowing JavaScript to handle long-running operations without blocking the execution of other code.

### Key Concepts of Callbacks 🔑

1. **Function as a First-Class Citizen**: In JavaScript, functions are "first-class citizens," meaning they can be treated like any other variable. You can pass functions as arguments, return them from other functions, and assign them to variables.

2. **Synchronous vs. Asynchronous Callbacks**:
   - **Synchronous Callbacks**: Executed immediately, as part of a regular function execution. These callbacks are used when you want to perform operations in a specific order without delays.
   - **Asynchronous Callbacks**: Executed after a specific event or operation completes, often without blocking other code from executing. These are typical in situations like network requests, timers, or reading files.

3. **How Callbacks Work**:
   - A callback function is passed to another function.
   - The main function executes and, once it reaches the callback point, invokes the callback function.
   - In asynchronous cases, the main function might continue executing without waiting for the callback.

### Examples of Callbacks in JavaScript 📝

#### 1. Simple Synchronous Callback ⏱️

```javascript
function greet(name) {
    console.log(`Hello, ${name}!`);
}

function getUserInput(callback) {
    const name = "Ravi";  // Simulated user input
    callback(name);
}

// Example Usage
getUserInput(greet);
```

In this case:
- `getUserInput` receives the function `greet` as a callback.
- Inside `getUserInput`, the `greet` function is called with the name `"Ravi"`.

#### 2. Asynchronous Callback with `setTimeout` ⏰

```javascript
function displayMessage() {
    console.log("This message is displayed after 2 seconds.");
}

setTimeout(displayMessage, 2000);  // Executes displayMessage after 2 seconds
```

- `setTimeout` is passed `displayMessage` as a callback function.
- `setTimeout` waits 2 seconds and then invokes `displayMessage`.

#### 3. Asynchronous Callback in HTTP Requests 🌐

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

### Callback Challenges: Callback Hell 🌪️

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

### Solutions to Callback Hell: Promises and Async/Await 🛠️

To handle asynchronous code more cleanly, JavaScript introduced **Promises** and later **async/await** syntax, which make chaining asynchronous actions easier and code more readable.

#### Using Promises 🤝

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

#### Using Async/Await ⏳

```javascript
async function executeTasks() {
    await firstTask();
    await secondTask();
    await thirdTask();
}

executeTasks();
```

With **async/await**, the code becomes simpler, looks synchronous, and avoids the deep nesting of callbacks.

### Summary 📋
- **Callbacks** are functions passed as arguments to other functions, especially useful in handling asynchronous operations.
- **Synchronous callbacks** execute immediately, while **asynchronous callbacks** execute after a specific event completes.
- **Callback hell** can make code difficult to read; **Promises** and **async/await** offer solutions to handle asynchronous code more cleanly.
- **Best practices**: Use named functions instead of anonymous ones for callbacks, limit callback nesting, and leverage Promises or async/await for complex asynchronous flows.

## ES6+ Features 🚀

### `let` and `const` 📦

ES6 introduced two new ways to declare variables: `let` and `const`. These provide block scope variables and constants in JavaScript.

- `let` allows you to declare variables that are limited in scope to the block, statement, or expression on which it is used.
- `const` allows you to declare variables that are constants, meaning their values cannot be reassigned.

Example:

```javascript
let x = 10;
const y = 20;

x = 15; // This is allowed
y = 25; // This will cause an error
```

### Arrow Functions 🏹

Arrow functions provide a shorter syntax for writing functions in JavaScript. They are anonymous and change the way `this` binds in functions.

Example:

```javascript
// Traditional function
function add(a, b) {
  return a + b;
}

// Arrow function
const add = (a, b) => a + b;
```

### Template Literals 📝

Template literals allow embedded expressions. You can use multi-line strings and string interpolation features with them.

Example:

```javascript
const name = 'Alice';
const greeting = `Hello, ${name}!`;
console.log(greeting); // Outputs: Hello, Alice!
```

## Asynchronous Programming ⏱️

### Promises 🤝

Promises are used to handle asynchronous operations in JavaScript. They represent a value that may be available now, or in the future, or never.

Example:

```javascript
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve('Success!');
  }, 1000);
});

promise.then((value) => {
  console.log(value); // Outputs: Success!
}).catch((error) => {
  console.error(error);
});
```

### Async/Await ⏳

Async/await is syntactic sugar built on top of promises. It allows you to write asynchronous code in a synchronous manner.

Example:

```javascript
async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
}

fetchData();
```

### Callbacks 📞

Callbacks are functions passed as arguments to other functions. They are used to handle asynchronous operations.

Example:

```javascript
function fetchData(callback) {
  setTimeout(() => {
    callback('Data fetched');
  }, 1000);
}

fetchData((data) => {
  console.log(data); // Outputs: Data fetched
});
```

## Best Practices and Coding Standards 📋

### Use `const` and `let` Instead of `var` ✅

Using `const` and `let` helps to avoid issues with variable hoisting and provides better scoping.

### Use Arrow Functions 🏹

Arrow functions provide a concise syntax and do not have their own `this`, which can help avoid common pitfalls with `this` in JavaScript.

### Use Template Literals 📝

Template literals make it easier to work with strings, especially when dealing with multi-line strings and string interpolation.

### Handle Errors Gracefully 🛡️

Always handle errors in your asynchronous code using `.catch` for promises or `try/catch` for async/await.

### Follow a Consistent Coding Style 🧹

Use a consistent coding style throughout your codebase. Tools like ESLint can help enforce coding standards.

## Recent Developments and Trends in JavaScript 🔮

### WebAssembly 🌐

WebAssembly (Wasm) is a binary instruction format for a stack-based virtual machine. It is designed to be a portable compilation target for high-level languages like C, C++, and Rust, enabling them to run on the web with near-native performance.

### Serverless Architecture ☁️

Serverless architecture allows you to build and run applications and services without having to manage infrastructure. AWS Lambda, Azure Functions, and Google Cloud Functions are popular serverless computing services.

### Modern JavaScript Frameworks 🛠️

Modern JavaScript frameworks like React, Vue, and Angular have become popular for building web applications. They provide powerful tools and abstractions for building complex user interfaces.

### Progressive Web Apps (PWAs) 📱

Progressive Web Apps are web applications that use modern web capabilities to deliver an app-like experience to users. They are reliable, fast, and engaging.

### TypeScript 📘

TypeScript is a superset of JavaScript that adds static types. It helps catch errors early through type checking and improves the development experience with better tooling and code navigation.
