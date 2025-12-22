React Hooks let developers use state, side effects, and other React features without writing class components. Hooks streamline code, improve readability, and promote a functional programming style, making functional components as powerful

### Types of React Hooks

1. State Hooks-: State hooks, specifically useState and useReducer, allow functional components to manage state in a more efficient and modular way. They provide an easier and cleaner approach to managing component-level states in comparison to class components.
2. Context Hooks-: The useContext hook in React is a powerful and convenient way to consume values from the React Context API in functional components. It allows functional components to access context values directly, without the need to manually pass props down through the component tree
3. Effect Hooks-:Effect hooks, specifically useEffect,useLayoutEffect, and useInsertionEffect, enable functional components to handle side effects in a more efficient and modular way.
4. Performance Hook
5. Resource Hook
6. Other Hooks and Custom Hooks

---

### useState

1. Initialize State: When you call useState(initialValue), it creates a state variable and an updater function.

  ``` const [count, setCount] = useState(0); ```

2. State is Preserved Across Renders: React remembers the state value between re-renders of the component. Each time the component renders, React keeps the latest value of count.

3. State Updates with the Updater Function: When you call setCount(newValue) React updates the state and it re-renders the component to reflect the new state value.

  ``` <button onClick={() => setCount(count + 1)}>Increment</button> ```  
  
4. Triggers Re-render: React will re-render only the component where useState was used—ensuring your UI updates automatically when the state changes.

- Example of counter using useState
  ```js
  import { useState } from 'react';
  export default function Counter() {
      const [count, setCount] = useState(0);
  
      function handleClick() {
          setCount(count + 1);
      }
      return (
          <button onClick={handleClick}>
              Click {count} me
          </button>
      );
  }
  ```
- Example of handling form input fields
  
  ```js
  import React, { useState } from 'react';
  
  function Form() {
      const [name, setName] = useState('');
      const [age, setAge] = useState('');
      const [submitted, setSubmitted] = useState(false);
  
      const handleSubmit = () => {
          setSubmitted(true);
      };
  
      return (
          <div>
              <input
                  type="text"
                  value={name}
                  onChange={(e) => setName(e.target.value)}
                  placeholder="Enter your name"
              />
              <input
                  type="number"
                  value={age}
                  onChange={(e) => setAge(e.target.value)}
                  placeholder="Enter your age"
              />
              <button onClick={handleSubmit}>Submit</button>
              {submitted && <p>Form Submitted!</p>}
          </div>
      );
  }
  
  export default Form;
  ```

  ---

  ### useEffect Hook
  
```
  useEffect(() => {
    // Code to run on each render
    return () => {
        // Cleanup function (optional)
    };
}, [dependencies]);
```
- Effect function: This is where your side effect code runs.
- Cleanup function: This optional return function cleans up side effects like subscriptions or timers when the component unmounts.
- Dependencies array: React re-runs the effect if any of the values in this array change

- How it works-:
1. Initial Render Happens: React renders the component and updates the DOM.
2. useEffect Executes After Render: It runs after the paint, not during render.
3. Dependencies Are Checked: If there is no dependency array, the effect runs after every render; if the array is empty ([]), it runs once on mount; if dependencies are provided, it runs only when those values change.
4. Cleanup Function Runs: Before the effect re-runs or the component unmounts, the cleanup function (returned from useEffect) is executed.
5. Effect Re-runs: If dependencies changed, the effect runs again—after cleanup.

  ```js
  //HookCounterOne.js
  
  // useEffect is defined here
  
  import { useState, useEffect } from "react";
  
  function HookCounterOne() {
      const [count, setCount] = useState(0);
  
      useEffect(() => {
          document.title = `You clicked ${count} times`;
      }, [count]);
  
      return (
          <div>
              <button onClick={() => setCount((prevCount) => prevCount + 1)}>
                  Click {count} times
              </button>
          </div>
      );
  }
  export default HookCounterOne;
  ```

- useEffect triggers a function on every component render, using React to execute specified tasks efficiently.
- Positioned within the component, it grants easy access to state and props without additional coding.
- To run useEffect on every render do not pass any dependency
- To run useEffect only once on the first render pass any empty array in the dependency
- To run useEffect on change of a particular value. Pass the state and props in the dependency array

---





