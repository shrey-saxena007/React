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
