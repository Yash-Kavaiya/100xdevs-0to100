# 2.6 | map, filter, arrow fns
Sure, let's break down these JavaScript concepts:

1. **Map Function**: The `map()` function in JavaScript creates a new array by calling a specific function on each element present in the original array[^10^]¹¹. It does not change the original array[^10^]. Here's an example of how it works:

```javascript
const numbers = [1, 4, 9];
const roots = numbers.map((num) => Math.sqrt(num));
// roots is now [1, 2, 3]
// numbers is still [1, 4, 9]
```

2. **Filter Function**: The `filter()` function creates a new array with elements that pass a test provided by a function¹². It does not change the original array¹. Here's an example:

```javascript
const numbers = [12, 5, 8, 130, 44];
const bigEnough = numbers.filter(num => num >= 10);
// bigEnough is [12, 130, 44]
```

3. **Arrow Functions**: Arrow functions were introduced in ES6 and allow us to write shorter function syntax⁶⁷. They are anonymous functions (i.e., functions without a name) but they are often assigned to a variable⁷. Here's an example:

```javascript
// Regular function
let multiply = function(a, b) {
  return a * b;
}

// Arrow function
let multiply = (a, b) => a * b;
```
In the arrow function above, `a` and `b` are parameters, while `a * b` is the body of the function. If the body requires additional lines of processing, it can be enclosed in `{}` brackets.

Remember, the handling of `this` is different in arrow functions compared to regular functions. In arrow functions, `this` always represents the object that defined the arrow function⁶.

I hope this helps! Let me know if you have any other questions.

Source: Conversation with Bing, 16/12/2023
(1) JavaScript Array map() Method - W3Schools. https://www.w3schools.com/jsref/jsref_map.asp.
(2) Array.prototype.map() - JavaScript | MDN - MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map.
(3) JavaScript Array filter() Method - W3Schools. https://www.w3schools.com/jsref/jsref_filter.asp.
(4) Array.prototype.filter() - JavaScript | MDN - MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter.
(5) JavaScript Arrow Function - W3Schools. https://www.w3schools.com/Js/js_arrow_function.asp.
(6) Arrow functions in JavaScript - GeeksforGeeks. https://www.geeksforgeeks.org/arrow-functions-in-javascript/.
(7) Guide to JavaScript's filter() Method - Stack Abuse. https://stackabuse.com/guide-to-javascripts-filter-method/.
(8) Filter() Method in Javascript with Example - STechies. https://www.stechies.com/filter-method-javascript/.
(9) Guide to the JavaScript Array Filter() Method | Built In. https://builtin.com/software-engineering-perspectives/javascript-filter.
(10) JavaScript Arrow Functions: A Step-By-Step Guide | Career Karma. https://careerkarma.com/blog/javascript-arrow-function/.
(11) Arrow functions in JavaScript - Coding Ninjas. https://www.codingninjas.com/studio/library/arrow-functions-in-javascript.
(12) Map JavaScript: A Guide to the .map() Method | Career Karma. https://careerkarma.com/blog/javascript-map/.
(13) JavaScript Array map() Method - GeeksforGeeks. https://www.geeksforgeeks.org/javascript-array-map-method/.
(14) JavaScript Map - GeeksforGeeks. https://www.geeksforgeeks.org/javascript-map/.