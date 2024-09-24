# React.js with TypeScript Workbook

## 1. Introduction to React.js

### What is React.js?

- **React.js** is a JavaScript library for building user interfaces, primarily for **single-page applications**.
- It is **declarative**, **component-based**, and maintains a **virtual DOM** to optimize rendering performance.

Key Features:
- **JSX**: A syntax extension allowing you to write HTML-like elements inside JavaScript.
- **Virtual DOM**: A lightweight representation of the actual DOM.
- **Component-based architecture**: Code is organized into reusable components.
- **Unidirectional data flow**: Data flows from parent to child components through **props**.
- **Hooks**: Functions that allow functional components to manage state and lifecycle.

---

## 2. Getting Started with React and TypeScript

### Setting up React with TypeScript
```bash
npx create-react-app my-app --template typescript
cd my-app
npm start
```
### Basic Folder Structure:
```css
my-app
│   README.md
│   package.json
│   tsconfig.json
└───src
    └───components
    └───App.tsx
    └───index.tsx
```

### JSX and TypeScript

```tsx
// App.tsx
import React from 'react';

const App: React.FC = () => {
  return (
    <div>
      <h1>Hello, React with TypeScript!</h1>
    </div>
  );
};

export default App;
```


## 3. Components and Props in TypeScript
### Functional Components with TypeScript
In TypeScript, we define component types explicitly for better type safety:

```tsx
// Greeting.tsx
import React from 'react';

interface GreetingProps {
  name: string;
}

const Greeting: React.FC<GreetingProps> = ({ name }) => {
  return <h2>Hello, {name}!</h2>;
};

export default Greeting;
```

### Using Props in a Parent Component

```tsx
// App.tsx
import React from 'react';
import Greeting from './components/Greeting';

const App: React.FC = () => {
  return (
    <div>
      <Greeting name="Francisco" />
    </div>
  );
};

export default App;
```

## 4. State Management with Hooks
### Using useState Hook with TypeScript

```tsx
// Counter.tsx
import React, { useState } from 'react';

const Counter: React.FC = () => {
  const [count, setCount] = useState<number>(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
};

export default Counter;

```

### Complex State with Objects


```tsx
// UserForm.tsx
import React, { useState } from 'react';

interface User {
  name: string;
  email: string;
}

const UserForm: React.FC = () => {
  const [user, setUser] = useState<User>({ name: '', email: '' });

  const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
    const { name, value } = e.target;
    setUser({ ...user, [name]: value });
  };

  return (
    <form>
      <input name="name" value={user.name} onChange={handleChange} />
      <input name="email" value={user.email} onChange={handleChange} />
      <p>
        Name: {user.name}, Email: {user.email}
      </p>
    </form>
  );
};

export default UserForm;

```

## 5. Event Handling
### Handling Input Changes

```tsx
// InputComponent.tsx
import React, { useState } from 'react';

const InputComponent: React.FC = () => {
  const [text, setText] = useState<string>('');

  return (
    <div>
      <input
        type="text"
        value={text}
        onChange={(e) => setText(e.target.value)}
      />
      <p>You typed: {text}</p>
    </div>
  );
};

export default InputComponent;

```

## 6. Conditional Rendering
### Ternary Operator

```tsx
// ConditionalRendering.tsx
import React from 'react';

interface WelcomeProps {
  isLoggedIn: boolean;
}

const Welcome: React.FC<WelcomeProps> = ({ isLoggedIn }) => {
  return isLoggedIn ? <h2>Welcome back!</h2> : <h2>Please log in</h2>;
};

export default Welcome;

```

## 7. Lists and Keys
### Rendering Lists

```tsx
// ItemList.tsx
import React from 'react';

interface Item {
  id: number;
  name: string;
}

const items: Item[] = [
  { id: 1, name: 'Item 1' },
  { id: 2, name: 'Item 2' },
  { id: 3, name: 'Item 3' },
];

const ItemList: React.FC = () => {
  return (
    <ul>
      {items.map((item) => (
        <li key={item.id}>{item.name}</li>
      ))}
    </ul>
  );
};

export default ItemList;

```

## 8. Forms and Controlled Components
### Handling Form Submission

```tsx
// SimpleForm.tsx
import React, { useState } from 'react';

const SimpleForm: React.FC = () => {
  const [name, setName] = useState<string>('');

  const handleSubmit = (e: React.FormEvent) => {
    e.preventDefault();
    console.log('Form submitted:', name);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="text"
        value={name}
        onChange={(e) => setName(e.target.value)}
      />
      <button type="submit">Submit</button>
    </form>
  );
};

export default SimpleForm;

```

## 9. Lifting State Up
### Sharing State Between Components


```tsx
// App.tsx
import React, { useState } from 'react';
import Child from './components/Child';

const App: React.FC = () => {
  const [data, setData] = useState<string>('');

  return (
    <div>
      <Child data={data} setData={setData} />
      <p>Data in App: {data}</p>
    </div>
  );
};

export default App;

// Child.tsx
import React from 'react';

interface ChildProps {
  data: string;
  setData: (value: string) => void;
}

const Child: React.FC<ChildProps> = ({ data, setData }) => {
  return (
    <div>
      <input
        type="text"
        value={data}
        onChange={(e) => setData(e.target.value)}
      />
    </div>
  );
};

export default Child;

```

## 10. Advanced Topics
### React Router with TypeScript

```bash
npm install react-router-dom
```

```tsx
// App.tsx
import React from 'react';
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';
import Home from './components/Home';
import About from './components/About';

const App: React.FC = () => {
  return (
    <Router>
      <Switch>
        <Route path="/" exact component={Home} />
        <Route path="/about" component={About} />
      </Switch>
    </Router>
  );
};

export default App;

```

