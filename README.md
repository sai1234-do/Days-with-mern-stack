# Day 1 – React Hooks (Kid Style 😄)

 🧠 What I learned
Today I learned how React remembers things and reacts to changes.



## 🟢 useState (Memory box)

Imagine React has a small box to remember numbers.

`js
const [count, setCount] = useState(0);
useEffect(() => {
  console.log("Component started");
}, []);
