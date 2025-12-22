Here’s a **quick, beginner-friendly explanation** 👇

---

## What is **Context** in React?

**Context** is a way to **share data globally** between components **without passing props again and again**.

👉 Normally, data flows like this:

```
Parent → Child → Grandchild → ...
```

This is called **prop drilling** and gets messy.

👉 **Context solves this** by letting any component directly access shared data.

---

## When do we use Context?

Use Context when data is needed by **many components**, like:

* Logged-in user info
* Theme (dark/light)
* Language
* App settings

---

## What is `useContext` hook?

`useContext` is a React hook that lets a component **read data from Context easily**.

Think of it like:

> “Give me the shared data from Context.”

---

## Simple Example (Step by Step)

### 1️⃣ Create Context

```js
import { createContext } from "react";

const UserContext = createContext();
```

---

### 2️⃣ Provide Context (Wrap your app)

```js
<UserContext.Provider value="Shrey">
  <App />
</UserContext.Provider>
```

➡️ Now `"Shrey"` is available to all child components.

---

### 3️⃣ Consume Context using `useContext`

```js
import { useContext } from "react";

const Profile = () => {
  const user = useContext(UserContext);

  return <h1>Hello {user}</h1>;
};
```

---

## Without Context vs With Context

❌ **Without Context**

```js
<App user={user}>
  <Profile user={user} />
</App>
```

✅ **With Context**

```js
const user = useContext(UserContext);
```

Much cleaner 👍

---

## One-line Summary

* **Context** = global data storage for React components
* **useContext** = hook to access that global data
* **Used to avoid prop drilling**

If you want, I can also explain this with a **real-life example (like WhatsApp login data)** or show a **diagram-style explanation**.
