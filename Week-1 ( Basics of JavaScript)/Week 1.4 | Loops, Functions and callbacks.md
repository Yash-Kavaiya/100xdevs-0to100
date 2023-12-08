# Loops
A `for` loop is a control flow statement that allows you to repeatedly execute a block of code a certain number of times or iterate over elements in an array or other iterable objects.

The basic syntax of a `for` loop looks like this:

```javascript
for (initialization; condition; increment/decrement) {
  // code to be executed
}
```

Let's break down the different parts of a `for` loop:

1. **Initialization:** It's where you initialize a counter variable. This is usually done using `let`, `var`, or `const` keywords in JavaScript. For example, `let i = 0;` initializes a variable `i` with a value of `0`.

2. **Condition:** It's the condition that is evaluated before each iteration of the loop. If this condition is `true`, the loop continues; if it's `false`, the loop stops. For example, `i < 5` checks if the variable `i` is less than `5`.

3. **Increment/Decrement:** This part is responsible for changing the value of the counter variable after each iteration. It can be an increment (`i++` or `i += 1`) to increase the counter variable, a decrement (`i--` or `i -= 1`) to decrease the counter variable, or any other operation that modifies the counter variable.

4. **Code Block:** This is the block of code enclosed within curly braces `{}`. It contains the statements that will be executed repeatedly until the condition becomes `false`.

Here's an example of a simple `for` loop that prints numbers from 0 to 4:

```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

This loop will:

- Start with `i = 0`.
- Check if `i` is less than `5`. If `true`, execute the code block.
- Print the value of `i`.
- Increment `i` by `1` (using `i++`).
- Repeat the process until `i` is no longer less than `5`.

The output of this loop will be:

```
0
1
2
3
4
```

`for` loops are versatile and commonly used for iterating over arrays, executing a block of code a specific number of times, or performing a series of operations until a certain condition is met. They provide a concise way to perform repetitive tasks in JavaScript.

Great way to visualise this - http://latentflip.com/loupe/

# Functions

### What is a function?
A function in JavaScript is a set of statements that performs a task or
calculates a value It should take some input and return an output where there is some obvious
relationship between the input and the output.

Functions in JavaScript are blocks of reusable code designed to perform a specific task or calculate a value. They help organize code, promote reusability, and facilitate better maintenance by breaking down complex tasks into smaller, manageable parts.

Here are key aspects and concepts related to functions in JavaScript:

### Function Declaration:

You can declare a function using the `function` keyword followed by the function name, parentheses `()`, and curly braces `{}` to define the function body.

```javascript
function greet() {
  console.log("Hello, world!");
}
```

### Function Parameters and Arguments:

Functions can take parameters, which are variables listed as a part of the function definition, allowing you to pass values into the function.

```javascript
function greetPerson(name) {
  console.log(`Hello, ${name}!`);
}

greetPerson("Alice"); // Output: Hello, Alice!
```

Here, `name` is a parameter. When calling `greetPerson("Alice")`, `"Alice"` is the argument passed to the `name` parameter.

### Return Statement:

Functions can return values using the `return` statement. This statement ends the function's execution and can pass a value back to the caller.

```javascript
function add(a, b) {
  return a + b;
}

const result = add(3, 5);
console.log(result); // Output: 8
```

The `add` function takes two arguments (`a` and `b`) and returns their sum.

### Function Expressions:

Functions can also be assigned to variables, forming function expressions. These can be named or anonymous.

```javascript
// Named function expression
const multiply = function multiplyNumbers(x, y) {
  return x * y;
};

// Anonymous function expression
const divide = function (a, b) {
  return a / b;
};
```

### Arrow Functions (ES6+):

Arrow functions provide a more concise syntax for writing functions. They are especially useful for short anonymous functions.

```javascript
const square = (x) => x * x;
```

### Higher-Order Functions:

JavaScript allows functions to be passed as arguments to other functions and returned as values from functions. Functions that accept other functions as arguments or return functions are called higher-order functions.

```javascript
function operateOnNumbers(x, y, operation) {
  return operation(x, y);
}

const resultAdd = operateOnNumbers(5, 3, (a, b) => a + b);
console.log(resultAdd); // Output: 8
```

### Scope:

Variables declared inside a function are typically only accessible within that function's scope unless they are explicitly returned or accessed via closures.

### Closures:

Closures allow functions to retain access to variables from their containing (enclosing) scope even after the outer function has finished executing.

Understanding functions in JavaScript is crucial for building applications, as they are fundamental building blocks of the language and play a significant role in structuring and organizing code.

# Callback Functions
Step 1 - Can you call one function inside another function?
Yes, you can call one function inside another function in JavaScript. This is a common practice and allows for better code organization and reusability. Functions can call other functions either by directly invoking them or by returning them as values and then invoking the returned function.

Here's an example demonstrating calling one function inside another function:

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

In this example, `greetAndWelcome` is a function that calls both `greet` and `welcome`. When `greetAndWelcome("Alice")` is called, it invokes the `greet` function with the provided name (`"Alice"`) and then calls the `welcome` function to display a welcome message.

Calling functions inside other functions is a powerful way to organize code and create modular and reusable pieces of functionality.