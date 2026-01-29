# Day 1 – React Hooks 

 🧠 What I learned
Today I learned how React remembers things and reacts to changes.



## 🟢 useState (Memory box)

Imagine React has a small box to remember numbers.

`js
const [count, setCount] = useState(0);
useEffect(() => {
  console.log("Component started");
}, []);
## Day 2 – React useEffect (Cleanup & Dependencies)

### 🔵 Dependency Array (React’s watch list 👀)

```js
useEffect(() => {
  console.log("I run when count changes");
}, [count]);useEffect(() => {
  const timer = setInterval(() => {
    console.log("Running...");
  }, 1000);

  return () => {
    clearInterval(timer);
    console.log("Cleaned up");
  };
}, []);Why cleanup is important
Prevents memory leaks
Stops unnecessary background work
Keeps app fast
#DAY 3 – React Props vs State (Student Explanation)
Props vs State (Clear Difference)
Feature
Props
State
Comes from
Parent
#state
const [count, setCount] = useState(0);
State is mutable
Changes cause re-render
Used for dynamic data
function Counter(props) {
  const [count, setCount] = useState(props.start);

  return (
    <div>
      <h3>{props.title}</h3>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>
        Increase
      </button>
    </div>
  );
}
Inside component
Can change?
❌ No
✅ Yes
Who owns it
Parent
Component
Usage
Pass data
Manage dataProps are read-only
Used to pass data
Flow is parent → child<Student name="Sai" />function Student(props) {
  return <h2>Name: {props.name}</h2>;
}
Today I learned:
What events are in React
How to handle button clicks
How React events are different from HTML
How to pass functions to events<button onclick="clickMe()">Click</button><button onClick={clickMe}>Click</button>function ClickExample() {
  function handleClick() {
    alert("Button clicked!");
  }

  return (
    <button onClick={handleClick}>
      Click Me
    </button>
  );
}
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  function increase() {
    setCount(count + 1);
  }

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increase}>+</button>
    </div>
  );
}
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  function increase() {
    setCount(count + 1);
  }

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increase}>+</button>
    </div>
  );
}
## 📅 Day 5 – Validations & REST APIs

### 🧠 What I learned today
Today I learned:
- What validation is and why it is important
- Frontend vs Backend validation
- What REST API is
- Common REST API methods and status codes

---

### 🔹 What is Validation?
Validation means checking user input before processing it.

Examples:
- Email should not be empty
- Password should have minimum length
- Name should contain only letters

Validation helps to:
- Prevent wrong data
- Improve user experience
- Protect backend/server

---

### 🔹 Frontend Validation (Client Side)

Frontend validation happens before sending data to the server.

```js
function handleSubmit(email, password) {
  if (email === "") {
    alert("Email is required");
    return;
  }

  if (password.length < 8) {
    alert("Password must be at least 8 characters");
    return;
  }

  alert("Form submitted successfully");
}