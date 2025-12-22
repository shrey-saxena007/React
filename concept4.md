- In React, events are actions that occur within an application, such as clicking a button, typing in a text field, or moving the mouse. React provides an efficient way to handle these actions using its event system. Event handlers like onClick, onChange, and onSubmit are used to capture and respond to these events.
``` <element onEvent={handlerFunction} /> ```
- events like-: onclick, onchange , onsubmit, 

---

### Handling Events in React
1. Adding Event Handlers-: In React, event handlers are added directly to elements via JSX attributes
2. Reading Props in Event Handlers-: In React, event handlers often need access to the props passed from parent components. This is useful when the event handler needs to perform actions based on the data provided via props.
3. Passing Event Handlers as Props-: Event handlers can be passed down to child components as props. This allows child components to communicate back to the parent and trigger actions in the parent when events occur.
4. Naming Event Handler Props-: In React, it’s common to name event handler props according to the event being handled. This helps in maintaining clarity and consistency in your codebase.




