# Introduction to JSX

**JSX** stands for JavaScript XML. It's a syntax extension to JavaScript, used with React to describe what the user interface should look like. Although it looks like HTML, JSX is neither a string nor HTML but a way to create React elements,

Consider this example:
```
const element = <h1>Hello, world!</h1>;
```
Here, &lt;h1&gt;Hello, world!&lt;/h1&gt; is JSX. It looks like HTML but is used to produce React elements.

# Embedding Expressions in JSX

You can embed any JavaScript expression in JSX by wrapping it in curly braces {}.
```
const name = 'Umar;
const element = <h1>Hello, {name}</h1>;
```

You can also embed the result of a JavaScript function:

```
function formatName(user) {
    return user.firstName + ' ' + user.lastName;
  }
  
  const user = {
    firstName: 'Umar',
    lastName: 'Tariq'
  };
  
  const element = (
    <h1>
      Hello, {formatName(user)}!
    </h1>
  );
```

Here, formatName(user) is a function call embedded in JSX.

# JSX as an Expression

JSX expressions are regular JavaScript expressions and can be used within if statements, loops, and more:

```
function getGreeting(user) {
    if (user) {
      return <h1>Hello, {formatName(user)}!</h1>;
    }
    return <h1>Hello, Stranger.</h1>;
  }
```

# Specifying Attributes with JSX

You can specify attributes in JSX using quotes for string literals:
```
const element = <a href="<https://www.reactjs.org"link</a>;
```
Or use curly braces for JavaScript expressions:
```
const element = <img src={user.avatarUrl}></img>;
```
**Note:** Do not combine quotes and curly braces for the same attribute.

# Self-closing tags
```
const element = <img src={user.avatarUrl} />;
```
# Security in JSX

React automatically escapes any embedded values to prevent injection attacks (XSS). For example:

```
const title = response.potentiallyMaliciousInput;
const element = <h1>{title}</h1>;
```

This ensures that any user input is converted to a string before rendering.

# JSX Represents Objects

JSX is compiled to React.createElement() calls:

```
const element = (
    <h1 className="greeting">
      Hello, world!
    </h1>
  );
```

is equivalent to:

```
const element = React.createElement(
    'h1',
    {className: 'greeting'},
    'Hello, world!'
  );
```

React.createElement() returns an object like this:

```
const element = {
    type: 'h1',
    props: {
      className: 'greeting',
      children: 'Hello, world!'
    }
  };  
```

These objects, called React elements, describe what to display on the screen. React uses these descriptions to construct and update the DOM.