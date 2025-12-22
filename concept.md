```js
import React from 'react';

function App() {
    return (
        <div>
            <h1>Hello World</h1>
        </div>
    );
}

export default App;
```

In this example:

- import React from 'react': Imports the React library to use React features in the component.
- function App() { ... }: Defines a React functional component called App.
- return ( ... ): The return statement renders HTML-like code (JSX) inside the component.
- <div>Hello World</div>: Displays a div element containing a heading (h1) with the text "Hello World."
- export default App: Exports the App component so it can be used in other files.


---

Exporting a component means making it available for use in other files. Importing a component means bringing it into another file to use it.
There are 2 types of export -:
1. default -: used in the last line of the file, with nme of the component to be exported
2. named-: using keyword export while creating the component(function)

---

## Components

In React, components are reusable, independent code blocks (A function or a class) that define the structure and behavior of the UI. They accept inputs (props or properties) and return elements that describe what should appear on the screen.

Types of Components-:

1. Functional Components
Functional components are simpler and preferred for most use cases. They are JavaScript functions that return React elements. With the introduction of React Hooks, functional components can also manage state and lifecycle events.
```js
function Greet(props) {
    return <h1>Hello, {props.name}!</h1>;
}
```
2. Class Components
Class components are ES6 classes that extend React.Component. They include additional features like state management and lifecycle methods.
```js
class Greet extends React.Component {
    render() {
        return <h1>Hello, {this.props.name}!</h1>;
  }
}
```

---
### Props in React Components

Props (short for properties) are read-only inputs passed from a parent component to a child component. They enable dynamic data flow and reusability.

- Props are immutable.
- They enable communication between components.

```js
function Greet(props) {
    return <h2>Welcome, {props.username}!</h2>;
}

// Usage
<Greet username="Anil" />;
```

---

### State in React Components
The state is a JavaScript object managed within a component, allowing it to maintain and update its own data over time. Unlike props, state is mutable and controlled entirely by the component.

- State updates trigger re-renders.
- Functional components use the useState hook to manage state.

```js

function Counter() {
    const [count, setCount] = React.useState(0);

    return (
        <div>
            <p>Count: {count}</p>
            <button onClick={() => 
                setCount(count + 1)}>Increment</button>
        </div>
    );
}

```

---

In React, you can nest components inside other components to build a modular and hierarchical structure.

---

Conditional rendering allows dynamic control over which UI elements or content are displayed based on specific conditions. It is commonly used in programming to show or hide elements depending on user input, data states, or system status

You can also manage conditional rendering based on the component's state. For example, you can show a loading spinner until some data is fetched, and then display the actual content once the data is ready.

Practical Condition Rendering

1. Displaying User Profile Based on Authentication
   You can conditionally render a user’s profile page if the user is logged in, or a login form if not.
    ```js
    import React, { useState } from 'react';

function App() {
    const [isAuthenticated, setIsAuthenticated] = useState(false);

    return (
        <div>
            {isAuthenticated ? (
                <h1>User Profile</h1>
            ) : (
                <button onClick={() => 
                    setIsAuthenticated(true)}>Log In</button>
            )}
        </div>
    );
}

export default App;
    ```

- The component uses useState to manage the isAuthenticated state, which is initially set to false.
- The isAuthenticated state determines what is rendered: if false, a "Log In" button is displayed; if true, a "User Profile" heading appears.
- When the "Log In" button is clicked, setIsAuthenticated(true) updates the state to true, triggering a re-render.
- After the state update, the button is replaced with "User Profile", demonstrating conditional rendering based on authentication state.


2. Showing Loading State
   You can display a loading spinner or message while waiting for data to be fetched.

   ```js
   import React, { useState, useEffect } from 'react';

function App() {
    const [isLoading, setIsLoading] = useState(true);
    const [data, setData] = useState(null);

    useEffect(() => {
        setTimeout(() => {
            setData('Fetched Data');
            setIsLoading(false);
        }, 2000);
    }, []);

    return (
        <div>
            {isLoading ? (
                <h1>Loading...</h1>
            ) : (
                <h1>{data}</h1>
            )}
        </div>
    );
}

export default App;
```


- The component uses useState to manage two state variables: isLoading (initially true) and data (initially null).
- The useEffect hook runs once after the component mounts and starts a setTimeout to simulate fetching data after 2 seconds.
- When the timeout completes, setData('Fetched Data') updates the data state, and setIsLoading(false) changes isLoading to false.
- The component initially renders "Loading...", and once the state updates, it re-renders to display "Fetched Data".




---


