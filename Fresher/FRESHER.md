# React Native Fresher Level

### Advanced TypeScript (Generics, Enums)

You should be comfortable with complex TypeScript: generics (e.g. `function identityt(arg: T): T {}`) and enums. This leads to safer, more maintainable code.

Generics in TypeScript allow for the creation of reusable components that can work with a variety of types. They introduce type variables, enabling functions, classes, and interfaces to operate on types passed as arguments. This avoids the need for repetitive code when handling different data types while maintaining type safety.

```typescript
function identity<Type>(arg: Type): Type {
  return arg;
}

let output1 = identity < string > "myString";
let output2 = identity(100); // Type inference
```

Enums (enumerations) in TypeScript provide a way to define a set of named constants. They enhance code readability and maintainability by replacing magic numbers or string literals with meaningful names. TypeScript supports numeric, string, and heterogeneous enums.

```typescript
enum Status {
  Pending,
  InProgress,
  Completed,
  Rejected,
}

let jobStatus: Status = Status.InProgress;
```

Enums can be declared with explicit values or rely on automatic assignment. By default, numeric enums start with 0 and increment by 1 for subsequent members. String enums require each member to be explicitly assigned a string literal value. Heterogeneous enums can mix numeric and string values but are generally discouraged due to potential confusion.

[Generics](https://www.typescriptlang.org/docs/handbook/2/generics.html)
[Enums](https://www.typescriptlang.org/docs/handbook/enums.html)

### State Management (Redux or Context API)

Entry-level devs should know how to manage global state. For example, Redux provides a predictable way to manage state. Redux describes itself as “a JS library for predictable and maintainable global state management”. Sample Redux setup:

```javascript
import { createStore } from "redux";
const reducer = (state = { count: 0 }, action) => {
  switch (action.type) {
    case "INCREMENT":
      return { count: state.count + 1 };
    default:
      return state;
  }
};
const store = createStore(reducer);
console.log(store.getState()); // {count: 0}
store.dispatch({ type: "INCREMENT" });
console.log(store.getState()); // {count: 1}
```

Alternatively, learn React’s Context API for simpler cases.
[Redux](https://redux.js.org/introduction/getting-started)
[React’s Context API](https://www.freecodecamp.org/news/context-api-in-react/)

### React Navigation (Stack, Tabs)

In React Native, navigating from one screen to another is a crucial aspect of app development. The most commonly used navigation libraries are React Navigation and React Native Navigation. Example using React Navigation:

```javascript
import { createStackNavigator } from "@react-navigation/stack";
const Stack = createStackNavigator();
// In App component’s return:
<NavigationContainer>
  <Stack.Navigator>
    <Stack.Screen name="Home" component={HomeScreen} />
    <Stack.Screen name="Details" component={DetailsScreen} />
  </Stack.Navigator>
</NavigationContainer>;
```

[React Navigation](https://reactnavigation.org/docs/getting-started)

### Debugging and Performance

Debugging is an essential aspect of the development workflow in React Native. Debugging in React Native is a crucial part of the development process, allowing developers to identify and fix issues in their applications.
You should use React Native’s DevTools and console logs for debugging. React Native provides a built-in Dev Menu and DevTools (based on Chrome DevTools) for inspecting code. Example: insert `console.log('value', myVar)` to inspect variables.
[Debugging Basics](https://reactnative.dev/docs/debugging)
[React Native DevTools](https://reactnative.dev/docs/react-native-devtools)
[Fast Refresh](https://reactnative.dev/docs/fast-refresh)

Performance is a crucial aspect of any application, and React Native is no exception. Optimizing performance in your React Native apps will not only lead to a better user experience but also lessen the load on device resources.
[Performance Overview](https://reactnative.dev/docs/performance)

### Collaboration and Deployment Basics

Even freshers should know Agile basics (Scrum tasks, code reviews) and how to deploy apps. Understand signing an app (keystores for Android) and submitting to App Store/Google Play. Tools like GitHub Actions for CI or Expo for easy deployment can be used.
[Publishing to Google Play Store](https://reactnative.dev/docs/signed-apk-android)
[Publishing to Apple App Store](https://reactnative.dev/docs/publishing-to-app-store)
