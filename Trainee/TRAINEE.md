# React Native Trainee Level

### Advanced JavaScript (ES6+ Features & Async)

Trainees need deeper JS skills: promises, async/await, destructuring, spread, and array methods. For example, using async/await for clear async code:

```javascript
async function fetchItems() {
  try {
    const response = await fetch("https://api.example.com/items");
    if (!response.ok) throw new Error(`Error: ${response.status}`);
    const items = await response.json();
    console.log(items);
  } catch (err) {
    console.error(err);
  }
}
fetchItems();
```

This makes asynchronous code read like sync code. Note that await “suspends execution” until the promise resolves, making code easier to write.
[Resources](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)

### TypeScript Deeper

Beyond basics, you should use TypeScript interfaces and generics to type props and state in React Native. Example:

```typescript
interface User {
  id: number;
  name: string;
}
const fetchUsers = async (): Promise<User[]> => {
  const res = await fetch("https://api.example.com/users");
  return await res.json();
};
```

Here fetchUsers promises to return an array of User. Typescript helps catch bugs early.
Resources:
[TypeScript Interfaces](https://www.typescriptlang.org/docs/handbook/interfaces.html)
[TypeScript Generics](https://www.typescriptlang.org/docs/handbook/2/generics.html)

### React Hooks and State Management

You should know React Hooks like useState, useEffect, and possibly useContext. Example:

```typescript
import React, { useState, useEffect } from "react";
import { Button, Text } from "react-native";

const Counter = () => {
  const [count, setCount] = useState(0);
  useEffect(() => {
    console.log("Count changed:", count);
  }, [count]);
  return (
    <>
      <Text>Count: {count}</Text>
      <Button title="Increment" onPress={() => setCount(count + 1)} />
    </>
  );
};
export default Counter;
```

Hooks let you handle state and side-effects

[Resources: React’s Hooks guide](https://react.dev/reference/react/hooks)

### React Native UI & Layout (Flexbox, Styling)

In React Native, layouts are primarily managed using the Flexbox styling system. Flexbox is a powerful and flexible layout system that allows you to create responsive and complex UIs using a set of simple rules.

You can use these styles in various combinations to create flexible layouts in React Native. Flexbox makes it easy to create responsive UIs that adapt to changes in screen size or orientation. Note that some of these styles might not work as expected in React Native compared to in CSS for the web, but the overall concepts remain the same.

You should master layout with Flexbox. For instance:

```javascript
const styles = StyleSheet.create({
  container: { flex: 1, justifyContent: "center", alignItems: "center" },
});
```

This centers content. Understanding flex, justifyContent, alignItems is crucial.
[Layout with Flexbox](https://reactnative.dev/docs/flexbox)
[Layout Props](https://reactnative.dev/docs/layout-props)

### Git Workflows

Beyond basic commits, you should use branches and pull requests. Example:

```bash
git checkout -b feature/login   # create new branch
git add .
git commit -m "Add login screen"
git push origin feature/login
```

Then open a pull request on GitHub/GitLab. Using branches for features and merging is standard.

[Git merge](https://www.atlassian.com/git/tutorials/using-branches/git-merge)
[Git Branch](https://www.atlassian.com/git/tutorials/using-branches)
[Git Branching and Merging](https://www.youtube.com/watch?v=Q1kHG842HoI)
[Git Branching and Merging: A Step-By-Step Guide](https://www.varonis.com/blog/git-branching)

### Consuming APIs (Fetch/Axios)

You should fetch data robustly and handle errors. Using a client like Axios can simplify requests. Example with Axios:

```javascript
import axios from "axios";
async function getData() {
  const res = await axios.get("https://api.example.com/data");
  console.log(res.data);
}
```

Axios is a popular promise-based HTTP client (similar to fetch). Use async/await and catch errors.
[Axios in React Native](https://www.geeksforgeeks.org/axios-in-react-native/)
[Using Axios with React Native to manage API requests](https://blog.logrocket.com/using-axios-with-react-native-manage-api-requests/)
