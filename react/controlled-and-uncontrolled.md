### 📘 **Definition of Controlled vs Uncontrolled Components in React**

---

### ✅ **Controlled Components**

> **A controlled component is a form element whose value is controlled by React state.**

* The value of the form element is **always set via state** (`useState`, `useForm`, etc.).
* Every input change triggers an **event handler** that updates the state.

#### Example:

```tsx
const [name, setName] = useState('');

<input value={name} onChange={(e) => setName(e.target.value)} />
```

#### Characteristics:

* React is the **single source of truth**.
* Allows easy validation, conditional rendering, and form state tracking.
* Re-renders on every keystroke.

---

### ❎ **Uncontrolled Components**

> **An uncontrolled component is a form element that manages its own state internally (via the DOM).**

* You use a **ref** to access the input’s value when needed (not during every change).
* React does **not** track the value in real-time.

#### Example:

```tsx
const inputRef = useRef();

<input ref={inputRef} />

// Later
console.log(inputRef.current.value);
```

#### Characteristics:

* The DOM is the **source of truth**.
* Useful for simple forms or when performance is key.
* Validation and tracking are manual.

---

### 🧠 Summary Table

| Feature         | Controlled                 | Uncontrolled           |
| --------------- | -------------------------- | ---------------------- |
| State Source    | React state (`useState`)   | DOM (`ref`)            |
| Value Access    | `value` prop               | `ref.current.value`    |
| Change Tracking | `onChange` handler         | No real-time tracking  |
| Validation      | Easier                     | Manual                 |
| Use Case        | Dynamic, interactive forms | Simple or legacy forms |
| Example Usage   | `value={state}`            | `ref={ref}`            |

---

### My Comments 
- use controlled only
- `React-hook-form` & `tanstack/react-form` are controlled only
- controlled components, easy to validate & manage
- controlled components, good for large form
