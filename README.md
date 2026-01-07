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