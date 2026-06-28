
2024-10-30 19:24

Status:

Tags:

![AD_4nXdIddvDN0O52jbiifpsJQfw47Ub3hlvGdBCNwpkrS42dqjj8EYOSOcndr1dajz29x_s9khIx7Xq2dPQ4agy_1IlBHcwIUhyCk8jAydh431LICGbr9f3GkfvLUyiEpFtHJ6tyzPemZ7TFnRDtwM2IA56ozMC=s800?key=z-Phy0DQGy9NMYcg5FdkkQ](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdIddvDN0O52jbiifpsJQfw47Ub3hlvGdBCNwpkrS42dqjj8EYOSOcndr1dajz29x_s9khIx7Xq2dPQ4agy_1IlBHcwIUhyCk8jAydh431LICGbr9f3GkfvLUyiEpFtHJ6tyzPemZ7TFnRDtwM2IA56ozMC=s800?key=z-Phy0DQGy9NMYcg5FdkkQ)

# React JS - Basic To Advance

> [!NOTE]
> React is a free and open source JavaScript library specifically designed for building user interfaces.

1. Developed By Facebook 2011
2. Use **Components** Model
3. Build Modular Apps
4. Learn Once, Write Anywhere

**Developed By Facebook** React is the most popular, powerful front-end library developed and sponsored by Facebook.

**Components Model**
A component is a peace of the UI that has it's own logic and appearance. A component can be small as a button or large as entire page.

**Components**
Components are independent & reusable bits of code. They serve the same purpose as JS functions, but work in isolation and return HTML.

Function reserved key word
```React.Jsx
const App () {
	return <div>Hello World</div>
}
```

Arrow function reserved key word
```React.jsx
const App = () {
	return <div>Hello World</div>
}
```


> Should first letter upper case, always return jsx content & export it.


REACT BASICS

### **1. What is React and what problem does it solve?**

- React is a JavaScript library for building user interfaces. 

- It allows developers to create reusable UI components and efficiently update the UI when the underlying data changes. 

- React's virtual DOM enables faster rendering by minimizing actual DOM manipulations.

### **2. How does React differ from other JavaScript frameworks?**

- Unlike traditional frameworks like Angular, React is focused solely on the view layer of the application. 

- It provides a component-based architecture, allowing developers to build encapsulated UI components that manage their state.

- React also utilizes a virtual DOM for performance optimization, which sets it apart from frameworks like jQuery.

### **3. What is JSX in React?**

- JSX is a syntax extension for JavaScript that allows developers to write HTML-like code within JavaScript. 

- It provides a more readable and concise way to define the structure of UI components in React. 

- JSX gets compiled to regular JavaScript by tools like Babel before being executed in the browser.

### **4. How do you create a component in React?**

In React, components can be created as either functional components or class components. 

Functional components are simple JavaScript functions that return JSX elements, while class components are ES6 classes that extend React. 

Components should implement a render method to return JSX.

### **5. What is the state in React?**

State in React represents the data a component needs to render and respond to user interactions. It is managed internally by the component and can be updated using the setState() method. When state changes, React automatically re-renders the component to reflect the new state.

### **6. Virtual DOM and Real DOM**

The **Real DOM** is the browser's actual representation of a web page's HTML structure. When a user interacts with the page, such as clicking a button or filling out a form, the browser updates the Real DOM to reflect the changes. These updates can be slow because the Real DOM directly manipulates the document and triggers re-rendering of the affected parts of the web page.

The **Virtual DOM**, on the other hand, is an in-memory abstraction of the Real DOM, created and maintained by JavaScript libraries like React. It is a lightweight copy of the Real DOM that allows for more efficient updates. When a user interacts with a React application, React updates the Virtual DOM first, compares it with its previous state (a process known as **diffing**), and calculates the minimal set of changes needed to update the Real DOM. This process, called **Reconciliation**, ensures that only the necessary updates are applied, significantly improving performance and reducing the time spent on rendering.

### **7. What are the advantages of using React?**

1. **Use Virtual DOM to improve efficiency:** React uses virtual DOM to render the view. As the name suggests, a virtual DOM is a virtual representation of the real DOM. Each time the data changes in a react app, a new virtual DOM gets created. Creating a virtual DOM is much faster than rendering the UI inside the browser. Therefore, with the use of virtual DOM, the efficiency of the app improves.

2. **SEO friendly:** React allows developers to develop engaging user interfaces that can be easily navigated in various search engines. It also allows server-side rendering, which boosts the SEO of an app.

3. **Reusable components:** React uses component-based architecture for developing applications. Components are independent and reusable bits of code. These components can be shared across various applications having similar functionality. The reuse of components increases the pace of development.

### **8. Server-side rendering(SSR) vs client-side rendering(CSR)**

Server-side rendering (SSR) and client-side rendering (CSR) are two approaches to rendering content for web applications. Both aim to deliver interactive web pages but differ in how and where the rendering process occurs.

 **Server-Side Rendering (SSR)**

![AD_4nXeZ1u-uzr6fdZYmm213TjQyxOlaUnrLFmhlxW5tdJPXY8QiGwW4mPVBrLXkGvQN0hR8jTNYCCkHgM5ad9dL9_HnQSbcnxT6S52XxPKngpoE6LXRifIE9HsigD0gneUKfct84Fr1ED8l0KE-q9m1nlVYC__F=s800?key=z-Phy0DQGy9NMYcg5FdkkQ](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeZ1u-uzr6fdZYmm213TjQyxOlaUnrLFmhlxW5tdJPXY8QiGwW4mPVBrLXkGvQN0hR8jTNYCCkHgM5ad9dL9_HnQSbcnxT6S52XxPKngpoE6LXRifIE9HsigD0gneUKfct84Fr1ED8l0KE-q9m1nlVYC__F=s800?key=z-Phy0DQGy9NMYcg5FdkkQ)
**In SSR, the application's code is executed on the server, and the server generates a fully- rendered HTML page that is sent to the user's browser.** 

Here’s how SSR works step by step:

1. The user enters a URL in the browser's address bar.
2. A request is sent to the server at the specified URL.
3. The server processes the request, retrieves data from a database (if necessary), and generates an HTML file containing the content and styles.
4. The server sends the fully-rendered HTML file back to the browser.
5. The browser displays the page immediately, often with minimal loading time.

**Advantages of SSR:**

- Faster initial page load, especially for users with slower internet connections.
- Improved SEO, as search engines can crawl fully-rendered pages.
- Better support for users with JavaScript disabled.

**Disadvantages of SSR:**

- Increased server load, as the server must render pages for each request.
- Slower page transitions for dynamic interactions, as the entire page must reload.

---
 **Client-Side Rendering (CSR)**

![AD_4nXfVP62gJBnj2UlWKV8Rz8WmHvwix810Dt6ag2ICCkIKcMrXKE0XbsqHrF3h53H5Xj46wHHpl4w6aFycPriNnX9lAJE_0gkEWbJdszbuLAi0wBu7nnhfwyZYyzRQ3VZLM5eveMx0AfqpqqLZSzSYMWJuZq3Z=s800?key=z-Phy0DQGy9NMYcg5FdkkQ](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfVP62gJBnj2UlWKV8Rz8WmHvwix810Dt6ag2ICCkIKcMrXKE0XbsqHrF3h53H5Xj46wHHpl4w6aFycPriNnX9lAJE_0gkEWbJdszbuLAi0wBu7nnhfwyZYyzRQ3VZLM5eveMx0AfqpqqLZSzSYMWJuZq3Z=s800?key=z-Phy0DQGy9NMYcg5FdkkQ)
**In CSR, the server sends raw data and JavaScript to the user's browser, where the rendering process happens. The browser uses JavaScript to build and render the page dynamically.** 

Here’s how CSR works step by step:

1. The user enters a URL in the browser's address bar.
2. A request is sent to the server at the specified URL.
3. The server retrieves the requested data (often in JSON format) and sends it to the browser along with JavaScript files.
4. The browser executes the JavaScript code, processes the data, and dynamically creates the content.
5. The rendered page is displayed to the user.

**Advantages of CSR:**

- Rich interactivity and smooth transitions between pages.
- Reduced server workload as the browser handles rendering.
- Modern frameworks (like React, Vue.js) enable reusable components and faster development.

**Disadvantages of CSR:**

- Slower initial load, as JavaScript must be downloaded, parsed, and executed.
- SEO challenges, as search engine bots may struggle with JavaScript-heavy pages.
- Performance issues for users with slow devices or older browsers.


 **Choosing Between SSR and CSR**

- **Use SSR** for content-heavy applications requiring fast initial load and better SEO, such as blogs, e-commerce sites, and news websites.
- **Use CSR** for applications with dynamic user interfaces and high interactivity, like social media platforms or dashboards.

### **9. What are the differences between functional and class components?**

Class components also known as stateful components contain state and lifecycle methods and are written with JavaScript ES6 classes. A state is an object that contains data that can be updated and displayed in the component. Lifecycle methods are called at different stages of the component’s life cycle, such as when it is updated.

Functional components are a simple, fast, and easy way to design and develop a component in React. They are used to create components that return JSX and don’t have their state.

Functional components take props as input and return a React element that describes what should be rendered on the screen. They are simpler to write and understand in comparison with class components. They are faster than class components as they do not have state and lifecycle methods. The functional component is also known as the stateless component as they do not handle states.

### **10. What are props in React?**

Props (short for "properties") in React are inputs passed to components. They are read-only and are used to pass data from a parent component to a child component. Props can be single values (e.g., strings, numbers) or objects containing multiple values.

Props are specified using a syntax similar to HTML attributes when creating a component. For example:

```jsx
<ChildComponent name="John" age={25} />
```

In this case, `name` and `age` are props passed to `ChildComponent`. The child component can access these props using the `props` object, like so:

```jsx
function ChildComponent(props) {
  return (
	<div>
	  <p>Name: {props.name}</p>
	  <p>Age: {props.age}</p>
	</div>
  );
}
	```

**Key Points:**

- Props are immutable, meaning they cannot be modified within the child component.
- They enable components to be reusable and dynamic.
- Props follow a unidirectional data flow (from parent to child).

### **11. What is a state in React?**

State in React is an object that holds dynamic data specific to a component. It determines the component's behavior and appearance, and changes to the state trigger a re-render of the component to reflect the updated data.

**Key Points About State:**

1. The state is managed within the component, making it private and fully controlled by that component.
2. Any change in the state values causes the component to re-render, ensuring the UI stays in sync with the current data.

**State in Class Components:**  
In class components, state is defined as an object and updated using the `setState()` method. For example:

```jsx
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  increment = () => {
    this.setState({ count: this.state.count + 1 });
  };

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.increment}>Increment</button>
      </div>
    );
  }
}
```
---
**State in Functional Components:**  
In functional components, state is managed using React Hooks, specifically the `useState()` hook. For example:

```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```
---
**Summary:**
- State allows React components to manage and respond to changes in data.
- Functional components do not have a built-in state object but can use React Hooks (`useState`) to manage state.
- Proper state management ensures an interactive and dynamic user interface.
### **12. What is prop drilling in React?**

Prop drilling in React refers to the process of passing data from a higher-level component down to deeply nested child components through multiple layers of intermediate components. 

This happens when a deeply nested component requires data or functions from a parent component, and the props must be passed explicitly through every intermediate component in the hierarchy.

#### **Example of Prop Drilling:**

```jsx
function Grandparent() {
  const message = "Hello from Grandparent!";
  return <Parent message={message} />;
}

function Parent({ message }) {
  return <Child message={message} />;
}

function Child({ message }) {
  return <div>{message}</div>;
}
```

In this example:
- The `message` prop originates in the `Grandparent` component.
- It is passed through the `Parent` component before finally reaching the `Child` component, even though the `Parent` component doesn’t use it directly.

#### **Challenges with Prop Drilling:**

- **Complexity:** As the component tree grows deeper, passing props through multiple layers becomes cumbersome and harder to manage.
- **Tight Coupling:** Intermediate components need to handle and pass props, even if they don’t use them, which increases coupling.

#### **Alternatives to Prop Drilling:**

To avoid prop drilling, you can use the following techniques:

1. **Context API:** Provides a way to pass data directly to deeply nested components without intermediate components having to pass the props explicitly.

```jsx
const MessageContext = React.createContext();

function Grandparent() {
  const message = "Hello from Grandparent!";
  return (
	<MessageContext.Provider value={message}>
	  <Child />
	</MessageContext.Provider>
  );
}

function Child() {
  const message = React.useContext(MessageContext);
  return <div>{message}</div>;
}
```

2. **State Management Libraries:** Tools like Redux, Zustand, or MobX help manage state globally, making it accessible to any component without passing props manually.

### **13. What is React Hooks?**

React Hooks are built-in functions introduced in React 16.8 that allow developers to use state and lifecycle methods in functional components. They simplify React development by enabling the same functionalities previously exclusive to class components, such as state management and side effects, in a more concise and reusable way.

#### **Key Features of React Hooks:**

1. **State Management:** Using the `useState` hook, functional components can maintain and update their state.
2. **Lifecycle Methods:** The `useEffect` hook enables functional components to manage side effects, like fetching data, directly replacing lifecycle methods like `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.
3. **Improved Code Reusability:** Hooks like `useContext` and custom hooks allow developers to share logic across components without repeating code.
4. **No Need for Class Components:** Hooks eliminate the need for class components, making functional components sufficient for most use cases.

#### **Component Lifecycle Phases in React:**

1. **Mounting:** The component is created and inserted into the DOM (e.g., initialization logic).
2. **Updating:** The component is updated when state or props change.
3. **Unmounting:** The component is removed from the DOM.

Hooks allow developers to navigate these phases using functions like `useEffect`.

#### **Example of React Hook (`useState`):**

Before React 16.8, state management required a class component:

```jsx
class Counter extends React.Component {
  state = { count: 0 };

  increment = () => this.setState({ count: this.state.count + 1 });

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.increment}>Increment</button>
      </div>
    );
  }
}
```

With hooks, the same functionality can be achieved in a functional component:

```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

#### **Commonly Used Hooks:**

1. `useState`: Manages state in a functional component.
2. `useEffect`: Handles side effects (e.g., API calls, subscriptions).
3. `useContext`: Accesses context without using `Context.Consumer`.
4. `useReducer`: Manages complex state logic.
5. `useRef`: Accesses DOM elements or persists values across renders.

#### **Hooks**

Here are some of the most commonly used React hooks, their purpose, properties, and code examples:

---
##### **1. `useState`**

**Purpose:** Manages state in functional components.  

**Properties:**
- Initial state is passed as an argument.
- Returns an array with the current state and a function to update it.

**Example:**

```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

---

##### **2. `useEffect`**

**Purpose:** Handles side effects such as data fetching, subscriptions, and DOM manipulations.  

**Properties:**
- Accepts a function as the first argument.
- The second argument is an optional dependency array to control when the effect runs.

**Example:**

```jsx
import React, { useState, useEffect } from 'react';

function Timer() {
  const [time, setTime] = useState(0);

  useEffect(() => {

    const interval = setInterval(() => {
      setTime((prevTime) => prevTime + 1);
    }, 1000);

    // Cleanup function to clear the interval when the component unmounts
    return () => clearInterval(interval);
  }, []); 
  // Empty dependency array ensures the effect runs only once when the component mounts

  return (
    <div>
      <p>Timer: {time} seconds</p>
    </div>
  );
}
```

---

The dependency array in `useEffect` controls when the effect runs. It’s not the same as a callback array but rather a mechanism to define the dependencies that trigger the effect. The dependency array determines **when and how often** the `useEffect` callback function runs. Let’s explore the different types of dependency arrays with examples.

---

##### **1. Empty Dependency Array (`[]`)**

- **Behavior:** The effect runs only once, after the component mounts.
- **Use Case:** When the effect does not depend on any dynamic values from props or state.

**Example: Fetch data on mount**

```jsx
import React, { useState, useEffect } from 'react';

function FetchData() {
  const [data, setData] = useState([]);

  useEffect(() => {
    fetch('https://jsonplaceholder.typicode.com/posts')
      .then((response) => response.json())
      .then((data) => setData(data));
  }, []); // Runs only once when the component mounts

  return (
    <div>
      <h2>Fetched Data:</h2>
      <ul>
        {data.map((item) => (
          <li key={item.id}>{item.title}</li>
        ))}
      </ul>
    </div>
  );
}
```

---

##### **2. Dependency Array with Specific Dependencies**

- **Behavior:** The effect runs only when the specified dependencies change.
- **Use Case:** When the effect depends on certain state or props values.

**Example: Update title based on a count**

```jsx
import React, { useState, useEffect } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `Count: ${count}`; // Updates the document title whenever count changes
  }, [count]); // Effect runs when `count` changes

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

---

##### **3. No Dependency Array**

- **Behavior:** The effect runs after every render (initial render and subsequent updates).
- **Use Case:** Rarely used; can lead to performance issues if not handled carefully.

**Example: Log something after every render**

```jsx
import React, { useState, useEffect } from 'react';

function RenderLogger() {
  const [value, setValue] = useState('');

  useEffect(() => {
    console.log('Component rendered');
  }); // No dependency array means this runs after every render

  return (
    <div>
      <input
        type="text"
        value={value}
        onChange={(e) => setValue(e.target.value)}
        placeholder="Type something"
      />
    </div>
  );
}
```

---

##### **4. Dependency Array with Multiple Dependencies**

- **Behavior:** The effect runs when **any** of the dependencies in the array change.
- **Use Case:** When the effect relies on multiple values.

**Example: Synchronize two states**

```jsx
import React, { useState, useEffect } from 'react';

function SyncState() {
  const [valueA, setValueA] = useState('');
  const [valueB, setValueB] = useState('');

  useEffect(() => {
    console.log(`Either valueA or valueB changed: A=${valueA}, B=${valueB}`);
  }, [valueA, valueB]); // Effect runs when `valueA` or `valueB` changes

  return (
    <div>
      <input
        type="text"
        value={valueA}
        onChange={(e) => setValueA(e.target.value)}
        placeholder="Value A"
      />
      <input
        type="text"
        value={valueB}
        onChange={(e) => setValueB(e.target.value)}
        placeholder="Value B"
      />
    </div>
  );
}
```

---

##### **5. Conditional Dependencies (Dynamic Dependencies)**

- **Behavior:** Dynamically add or remove dependencies based on a condition.
- **Use Case:** When dependencies are determined during runtime.

**Example: Conditionally update based on a flag**

```jsx
import React, { useState, useEffect } from 'react';

function ConditionalEffect() {
  const [count, setCount] = useState(0);
  const [updateEffect, setUpdateEffect] = useState(false);

  useEffect(() => {
    if (updateEffect) {
      console.log('Effect ran because updateEffect is true');
    }
  }, [updateEffect ? count : null]); // Effect runs only if updateEffect is true

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
      <button onClick={() => setUpdateEffect(!updateEffect)}>
        Toggle Effect Trigger
      </button>
    </div>
  );
}
```

---

##### **Key Takeaways**

1. **Empty Dependency Array (`[]`):** Effect runs once on mount.
2. **No Dependency Array:** Effect runs after every render (initial + updates).
3. **Specific Dependencies:** Effect runs only when specified dependencies change.
4. **Multiple Dependencies:** Effect runs when any dependency changes.
5. **Dynamic Dependencies:** Customize dependencies based on conditions.

Choosing the right dependency array depends on the effect's purpose and when you want it to run.

##### **3. `useContext`**

**Purpose:** Provides a way to share values (e.g., theme, user info) across the component tree without prop drilling.  

**Properties:**
- Works with `React.createContext()` to manage shared state or logic.
- Accesses context values directly using the hook.

**Example:**

```jsx
import React, { createContext, useContext } from 'react';

const ThemeContext = createContext('light');

function ThemeDisplay() {
  const theme = useContext(ThemeContext);
  return <p>Current Theme: {theme}</p>;
}

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <ThemeDisplay />
    </ThemeContext.Provider>
  );
}
```

---

##### **4. `useReducer`**

**Purpose:** Manages complex state logic, especially useful for scenarios involving multiple state transitions.  

**Properties:**
- Accepts a reducer function and an initial state.
- Returns the current state and a dispatch function.

**Example:**

```jsx
import React, { useReducer } from 'react';

const initialState = { count: 0 };

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return { count: state.count + 1 };
    case 'decrement':
      return { count: state.count - 1 };
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);

  return (
    <div>
      <p>Count: {state.count}</p>
      <button onClick={() => dispatch({ type: 'increment' })}>Increment</button>
      <button onClick={() => dispatch({ type: 'decrement' })}>Decrement</button>
    </div>
  );
}
```

---

##### **5. `useRef`**

**Purpose:**
- Accesses DOM elements directly.
- Persists mutable values across renders without causing re-renders.

**Properties:**
- Returns a mutable object with a `current` property.
- Can also store a reference to a value or DOM node.

**Example:**

```jsx
import React, { useRef } from 'react';

function FocusInput() {
  const inputRef = useRef(null);

  const handleFocus = () => {
    inputRef.current.focus(); // Access the input element and call its focus method
  };

  return (
    <div>
      <input ref={inputRef} type="text" placeholder="Type something" />
      <button onClick={handleFocus}>Focus Input</button>
    </div>
  );
}
```

---

##### **6. `useMemo`**

**Purpose:** Optimizes performance by memoizing expensive computations.  

**Properties:**
- Accepts a computation function and a dependency array.
- Only re-computes the value when dependencies change.

**Example:**

```jsx
import React, { useState, useMemo } from 'react';

function Fibonacci() {
  const [num, setNum] = useState(1);
  const [increment, setIncrement] = useState(0);

  const fib = useMemo(() => {
    const computeFib = (n) => (n <= 1 ? n : computeFib(n - 1) + computeFib(n - 2));
    return computeFib(num);
  }, [num]); // Only recalculates when `num` changes

  return (
    <div>
      <p>Fibonacci of {num}: {fib}</p>
      <button onClick={() => setNum(num + 1)}>Next</button>
      <button onClick={() => setIncrement(increment + 1)}>Increment Counter</button>
    </div>
  );
}
```

---

These hooks are widely used in React development to simplify state management, improve performance, and enhance code reusability.


### **14. What are the different phases of the React component’s lifecycle?**

Initial Rendering Phase: This is the phase when the component is about to start its life journey and make its way to the DOM.

Updating Phase: Once the component gets added to the DOM, it can potentially update and re-render only when a prop or state change occurs. That happens only in this phase.

Unmounting Phase: This is the final phase of a component’s life cycle in which the component is destroyed and removed from the DOM.

Here’s a detailed breakdown of the React component lifecycle phases, with clarification and additional context:

---

#### **1. Initial Rendering Phase**

- **Description:** This is the phase when a component is created and inserted into the DOM for the first time.
- **Key Methods:**
    - **`constructor` (Class Components):** Used for initializing state and binding methods.
    - **`componentDidMount` (Class Components):** Called after the component is rendered into the DOM.
    - **`useEffect` (Functional Components):** Can be used with an empty dependency array `[]` to mimic `componentDidMount`.

**Example:**

```jsx
import React, { useState, useEffect } from 'react';

function InitialRender() {
  useEffect(() => {
    console.log('Component mounted for the first time.');
  }, []); // Mimics componentDidMount

  return <div>Initial Rendering Phase</div>;
}
```

---

#### **2. Updating Phase**

- **Description:** This phase occurs when a component's state or props are updated, causing the component to re-render.
- **Key Methods:**
    - **`componentDidUpdate` (Class Components):** Called after every update.
    - **`shouldComponentUpdate` (Class Components):** Used to optimize rendering by returning `true` or `false`.
    - **`useEffect` (Functional Components):** Handles updates when dependencies in the array change.

**Example:**

```jsx
import React, { useState, useEffect } from 'react';

function UpdatingPhase() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    console.log(`Component updated: Count is now ${count}`);
  }, [count]); // Runs whenever count changes

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

---

#### **3. Unmounting Phase**

- **Description:** This is the cleanup phase when a component is removed from the DOM and destroyed.
- **Key Methods:**
    - **`componentWillUnmount` (Class Components):** Cleanup tasks like unsubscribing from listeners or clearing intervals.
    - **`useEffect` Cleanup Function (Functional Components):** Used for cleanup when the component is unmounted.

**Example:**

```jsx
import React, { useState, useEffect } from 'react';

function TimerComponent() {
  const [time, setTime] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setTime((prevTime) => prevTime + 1);
    }, 1000);

    return () => {
      console.log('Component is unmounting, clearing interval.');
      clearInterval(interval);
    };
  }, []); // Runs once, mimicking componentDidMount and componentWillUnmount

  return <p>Timer: {time} seconds</p>;
}
```

---

#### Lifecycle Phases in Class Components vs. Functional Components

|**Phase**|**Class Components**|**Functional Components**|
|---|---|---|
|**Initial Rendering**|`constructor`, `componentDidMount`|`useEffect(() => {...}, [])`|
|**Updating**|`componentDidUpdate`, `shouldComponentUpdate`|`useEffect(() => {...}, [dependencies])`|
|**Unmounting**|`componentWillUnmount`|Cleanup function in `useEffect`|

---

#### Summary of Lifecycle Phases

1. **Initial Rendering Phase:**
    - The component is created and inserted into the DOM.
    - Hooks: `useEffect(() => {...}, [])`.
2. **Updating Phase:**
    - Triggered by state or props changes.
    - Hooks: `useEffect(() => {...}, [dependencies])`.
3. **Unmounting Phase:**
    - The component is removed from the DOM.
    - Hooks: Cleanup inside `useEffect`.

React’s functional components simplify lifecycle management using `useEffect`, making the code more concise and easier to maintain.

### **15. Explain the lifecycle methods of React components in detail.**

Some of the most important lifecycle methods are:

1. **componentWillMount()** – Executed just before rendering takes place both on the client and well as server-side.
2. **componentDidMount()** – Executed on the client side only after the first render.
3. **componentWillReceiveProps()** – Invoked as soon as the props are received from the parent class and before another render is called.
4. **shouldComponentUpdate()** – Returns true or false value based on certain conditions. If you want your component to update, return true else return false. By default, it returns false.
5. **componentWillUpdate()** – Called just before rendering takes place in the DOM.
6. **componentDidUpdate()** – Called immediately after rendering takes place.
7. **componentWillUnmount()** – Called after the component is unmounted from the DOM. It is used to clear up the memory spaces.

### **16. What is  React Router?**

**React Router** is a standard routing library for React applications, providing a way to navigate between different views or pages within a single-page application (SPA) without reloading the entire page. It allows you to manage URL paths and map them to specific components or views, keeping the URL in sync with the content being displayed on the web page. React Router makes it easier to build dynamic navigation and is a core tool for implementing multi-page navigation in a React-based SPA.

Key features of React Router include:

1. **Dynamic Routing:** React Router enables dynamic routing, meaning routes can be added or removed based on the current state or conditions of the application.

2. **URL Mapping:** It provides a way to map URL paths to components, keeping the URL and displayed data in sync.
    
3. **Client-Side Routing:** React Router enables client-side routing, which means that navigation between pages happens without reloading the entire page, making the application faster and smoother.
    
4. **Nested Routing:** React Router allows nested routes, making it possible to render child components within parent components, helping with complex views.
    
5. **Declarative Routing:** Routes are defined using declarative syntax in JSX, making it easier to understand and manage routes.
    

#### **Basic Components of React Router:**

1. **`<BrowserRouter>`**: A wrapper component that uses the HTML5 history API to keep the UI in sync with the URL.
    
2. **`<Route>`**: Defines a mapping between a URL path and a component that should be rendered when the path is matched.
    
3. **`<Switch>`**: Renders the first route that matches the current location. It helps to prevent multiple components from rendering simultaneously.
    
4. **`<Link>`**: A component used for navigation, it prevents full-page reloads and allows for navigation within the React application.
    
5. **`<Redirect>`**: Redirects the user to another route based on certain conditions.
    
6. **`useHistory`, `useLocation`, `useParams`, `useRouteMatch`**: React Router hooks that give access to navigation and route data within functional components.
    

#### **Basic Example of React Router:**

```jsx
import React from 'react';
import { BrowserRouter as Router, Route, Switch, Link } from 'react-router-dom';

function Home() {
  return <h2>Home Page</h2>;
}

function About() {
  return <h2>About Page</h2>;
}

function NotFound() {
  return <h2>404 - Not Found</h2>;
}

function App() {
  return (
    <Router>
      <nav>
        <ul>
          <li>
            <Link to="/">Home</Link>
          </li>
          <li>
            <Link to="/about">About</Link>
          </li>
        </ul>
      </nav>

      <Switch>
        <Route exact path="/" component={Home} />
        <Route path="/about" component={About} />
        <Route component={NotFound} /> {/* This will render if no other route matches */}
      </Switch>
    </Router>
  );
}

export default App;
```

#### **Key Concepts:**

- **Routing Path Matching:** React Router matches the current URL to a path defined in a `<Route>` component.
- **Component-based Navigation:** Instead of traditional page navigation, React Router uses components that are rendered based on the route.
- **Declarative Navigation:** React Router provides declarative navigation using components like `<Link>` instead of traditional `<a>` tags.

#### **React Router Versions:**

React Router has undergone several major updates, with version 6 introducing significant changes in how routing is handled:

- Version 6 introduced features like **`Route`** element changes (replacing `component` prop with `element`), **`useNavigate`** for navigation, and improved handling of nested routes.

React Router helps developers build smooth, single-page navigation experiences while maintaining the power and flexibility of traditional multi-page applications.

**JSX**

JSX allows us to write HTML in React. 
JSX makes it easier to write & add HTML in React.

Simply means js xml. Illusion of js react compiler convert these in to js and compile it.
JSX component only allows one parent.

![[Pasted image 20241030213527.png]]




**{ Expressions In JSX }**
With JSX you can write expressions inside curly braces. The expressions can be a React variable, or
property, or any other valid JavaScript expression.

JSX will execute the expression and return the result.

![[Pasted image 20241030215716.png]]

![[Pasted image 20241030215731.png]]


![[Pasted image 20241030215802.png]]

**LISTS**
In React, you will render lists with some type of loop. The JavaScript map() array method is generally the preferred method.

![[Pasted image 20241030221552.png]]


![[Frontend interview questions 2025_Frontend developer 2025.pdf]]


![[Interview Guidebook.pdf]]
# Reference