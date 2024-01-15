# React
React is just an easier way to write normal HTML/CSS/JS
 It’s a new syntax, that under the hood gets converted to HTML/CSS/JS

- State
- components
- re-rendering

React.js is a popular JavaScript library for building user interfaces, particularly for single-page applications. Here are some reasons why developers choose to use React.js:

1. **Flexibility**: React.js is remarkably flexible. It's a library, not a framework, which means it can be used on a variety of platforms to build quality user interfaces¹.

2. **Component-Based**: React.js was created with a focus on building components for web applications. A React component can be anything in your web application like a Button, Text, Label, or Grid¹.

3. **Performance**: React.js has great performance due to its virtual DOM implementation and various rendering optimizations¹.

4. **Community Support**: React.js has broad community support and Facebook's backing. It's used by many Fortune 500 companies¹.

5. **Ease of Learning**: React.js has a shallow learning curve, making it a good choice for developers who want to build highly responsive, beautiful components⁵.

6. **Reusable Components**: React.js allows developers to create reusable UI components, which reduces development time and provides a responsive user interface².

## Why React?

https://react.dev/

- People realised it’s harder to do DOM manipulation the conventional way
- There were libraries that came into the picture that made it slightly easy, but still for a very big app it’s very hard (JQuery)
- Eventually, VueJS/React created a new syntax to do frontends
- Under the hood, the react compiler convert your code to HTML/CSS/JS

Let’s look at a simple example

Problem with this approach
1. Too much code you have to write as the developer
2. As your app scales (todo app for eg), this gets
harder and harder.

1. State
2. Components

Creators of frontend frameworks realised that all websites can effectively be divided into two parts

### State/Components/Re-rendering
- An object that represents the current state of the app It represents the dynamic things in your app (things that change)
For example, the value of the counter

### Components

How a DOM element should render, given a state
It is a re-usable, dynamic, HTML snippet that changes given the state

A state change triggers a re-render
A re-render represents the actual DOM being manipulated
when the state changes

You usually have to define all your components once And then all you have to do is update the state of your app, React takes care of re-rendering your app



