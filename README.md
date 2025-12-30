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