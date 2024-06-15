# ****Introduction to React****

React is a JavaScript library for building user interfaces. It allows developers to create large web applications that can update and render efficiently in response to data changes. React is component-based, meaning the UI is divided into small, reusable pieces called components.

# Adding React to an HTML Page
```
<!DOCTYPE html>
<html lang="en">
<title>Test React</title>

<!-- Load React API -->
<script src= "https://unpkg.com/react@16/umd/react.production.min.js"></script>
<!-- Load React DOM-->
<script src= "https://unpkg.com/react-dom@16/umd/react-dom.production.min.js"></script>
<!-- Load Babel Compiler -->
<script src="https://unpkg.com/babel-standalone@6.15.0/babel.min.js"></script>

<body>

<script type="text/babel">
    //  JSX Babel code goes here
</script>

</body>
</html>

```

# What is Babel?

Babel is a JavaScript compiler that can translate markup or programming languages into JavaScript. React uses Babel to convert JSX into JavaScript.

Please note that &lt;script type="text/babel"&gt; is needed for using Babel

# JSX

JSX, which stands for JavaScript XML, is a syntax extension for JavaScript that looks similar to HTML or XML. It's commonly used with React to describe the UI structure

- JSX allows you to write HTML-like code within JavaScript.
- It gets transpiled into regular JavaScript by tools like Babel.
- JSX example const element = &lt;h1&gt;Hello, World!&lt;/h1&gt;;
- JSX tags can represent HTML elements (&lt;div&gt;, &lt;span&gt;, etc.) or React components (&lt;MyComponent&gt;).
- JSX attributes are similar to HTML attributes but can take JavaScript expressions by using curly braces {}.

# React DOM Render

The method ReactDom.render() is used to render (display) HTML elements:

```
<div id="id01">Hello World!</div>

<script type="text/babel">
const name = 'John Doe';
ReactDOM.render(
    <h1>Hello {name}!</h1>,
    document.getElementById('id01'));
</script>
```

# DOM in React

## What is the DOM?

The **Document Object Model (DOM)** is a programming interface for web documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects; that way, programming languages can interact with the page.

## How React Uses the DOM

React is a JavaScript library for building user interfaces. It efficiently updates and renders just the right components when your data changes. React achieves this efficiency with the help of the **Virtual DOM**.

## Virtual DOM

The Virtual DOM is a concept where a virtual representation of the real DOM is kept in memory. React uses this virtual representation to perform efficient updates.

## How the Virtual DOM Works

1. **Initial Render:**
    - When a React component is rendered for the first time, a virtual DOM tree is created from the JSX code. This virtual DOM tree is then used to generate the real DOM nodes that are inserted into the document.
2. **Updating the DOM:**
    - When the state of a component changes, React creates a new virtual DOM tree representing the updated state.
    - React then compares this new virtual DOM tree with the previous one using a process called **reconciliation**.
    - This comparison, or diffing algorithm, identifies what parts of the real DOM need to be changed.
3. **Efficient Updates:**
    - Once the differences are identified, React updates only the parts of the real DOM that have changed. This minimizes the number of direct DOM manipulations, which can be slow and costly in terms of performance.
    - React batches updates to the DOM to further improve performance.

# React Elements and Rendering

React elements are the building blocks of React applications. They represent what you want to see on the screen and can be created using JSX

## The Root Element

React applications are typically structured around a single HTML element, often referred to as the root element. This is where the entire React component tree gets rendered.

&lt;div id="root"&gt;&lt;/div&gt;

## Creating React Elements

React elements are created using JSX, which allows you to write HTML-like syntax within JavaScript. Here’s an example of creating a simple React element:

const element = &lt;h1&gt;Hello, React!&lt;/h1&gt;;

## Rendering React Elements

To display a React element on the screen, you use the ReactDOM.render() method. This method takes two arguments:

1. The React element you want to render.
2. The DOM node where you want to render the element (the root element).

```
// Import React and ReactDOM libraries
import React from 'react';
import ReactDOM from 'react-dom';

// Create a React element
const element = <h1>Hello, React!</h1>;

// Render the element into the root element
ReactDOM.render(element, document.getElementById('root'));
```

# **React Elements are Immutable:**

You cannot change an element once it's created. Instead, create a new element whenever an update is required. To update the UI, render a new element using ReactDOM.render().

# React Components

React components are JavaScript functions.

function Welcome() {

&nbsp;   return &lt;h1&gt;Hello React!&lt;/h1&gt;;

}

ReactDOM.render(&lt;Welcome /&gt;, document.getElementById('root'));

## React Component Properties

function Welcome(props) {

&nbsp;   return &lt;h1&gt;Hello {props.name}!&lt;/h1&gt;;

}

ReactDOM.render(&lt;Welcome name="John Doe"/&gt;, document.getElementById('root'));

# Create React App (CRA)

Create React App (CRA) is a tool developed by Facebook to set up a new React project with a standard structure and configuration. It simplifies the process of setting up a React development environment by providing everything you need out of the box, including:

- A development server that uses Webpack to compile React, JSX, and ES6.
- Automatic CSS prefixing.
- ESLint configuration to test and warn about code mistakes.
- **Node.js**: Ensure you have Node.js version 5.2 or higher.

## Installation Steps

1. **Install npx (if not already installed)**

If you don't have npx installed, you can install it using npm:

npm install -g npx

2. **Create a New React Application**

Use the following command in your terminal to create a new React application. Replace react-tutorial with your desired project name:

npx create-react-app react-tutorial

3. **Navigate to Your Project Directory**

After the setup is complete, navigate to your project directory:

cd react-tutorial

4. **Start the Development Server**

To start the development server, use the following command:

npm start

This will start a local development server and open your new React application in your default web browser.