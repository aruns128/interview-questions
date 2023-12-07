HTML:

1. What is the purpose of the <!DOCTYPE> declaration?
   The <!DOCTYPE> declaration specifies the document type and version of HTML being used, helping browsers render the page correctly. 
2. What are void elements in HTML?
   Void elements (self-closing tags) are elements that do not have a closing tag, such as <img>, <br>, and <input>.
3. What is the purpose of the <meta> tag?
   The <meta> tag provides metadata about the HTML document, including character encoding, viewport settings, and more.
4. Explain the difference between the <span> and <div> elements.
   The <span> element is an inline container for styling or scripting, while the <div> element is a block-level container for layout and styling.
5. How do you link external CSS and JavaScript files to an HTML document?
   You can use the <link> tag to link external CSS files and the <script> tag to link external JavaScript files.
6. give some sample semantic HTML
   <video>,<audio>,<footer>,<header>,<aside>,<section>

CSS:

1. Question: Explain the difference between an ID selector and a class selector.
   An ID selector targets a single unique element using its `id` attribute, while a class selector targets one or more elements that share the same class name. 
2. Describe the components of the box model ?
   The box model consists of content, padding, border, and margin. - 0
3. Differentiate between `display: block`, `display: inline` ?
   `display: block` makes an element a block-level element, taking up the full width available and starting on a new line. `display: inline` makes an element an inline element, allowing other elements to be on the same line. - 1
4. Provide an example of using media queries to adapt a layout for mobile devices(768px).

```css
@media (max-width: 768px) {
  .header {
    font-size: 18px;
  }
} - 1
```

5. how we can center the element in div ?

- d:flex,j-c:center,a-i:c
- d:grid,place-items:"center" - 0

Javascript:

1. Is Javascript Asynchronous or synchronous, Difference between Asynchronous vs synchronous, --- stack

```javascript
console.log("console 1");
setTimeout(() => {
  console.log("console 2");
}, 1000);
setTimeout(() => {
  console.log("console 3");
}, 0);
console.log("console 4");
```

- how to handle asynchronous in javascript ?

example:

```javascript
const x = 10,
console.log(x)
```

how this program executed in javascript ?

- Compilation Phase:
  It performs tasks like tokenization and parsing to create an abstract syntax tree (AST) representing the code's structure. In this phase, the engine also identifies variable declarations, function declarations, and other syntax elements.
- Execution Phase:

  Once the compilation is done, the JavaScript engine moves to the execution phase. It follows the execution process based on the prepared AST and performs the following steps:

  a. Memory Allocation: In the memory, space is allocated for the variables and functions that are identified during the compilation phase. In this case, memory is allocated for the constant variable x.

  b. Initialization: The const x = 10; line is executed. The value 10 is assigned to the constant variable x.

  c. Execution of Statements: The console.log(x); line is executed. The engine looks up the value of x (which is 10) and passes it as an argument to the console.log() function.

  d. Output: The console.log() function displays the value of x (10) to the console.

- hoisting - 1
- difference between arrow function and Regular Function - 0
- which one is hoisting first arrow function or Regular Function

```javascript
// Named function expression - hoisted entirely
namedFunctionExpression(); // This works even before the function expression

var namedFunctionExpression = function () {
  console.log("This is a named function expression.");
};

// Arrow function expression - variable declaration is hoisted, assignment isn't
// This will result in an error: arrowFunctionExpression is not a function
arrowFunctionExpression();

const arrowFunctionExpression = () => {
  console.log("This is an arrow function expression.");
};

--------

namedFunctionExpression();
var namedFunctionExpression = function () {
  console.log("This is a named function expression.");
};
arrowFunctionExpression();
const arrowFunctionExpression = () => {
  console.log("This is an arrow function expression.");
}; - 0
```

2. Question: Explain what will be printed when the following code is executed:

```javascript
function outer() {
  var x = 10;
  function inner() {
    console.log(x);
  }
  return inner;
}

var closureFn = outer();
closureFn(); // What will be printed?
```

3. Create a button element on a webpage. Add an event listener to the button so that when it's clicked, an alert says "Button clicked!"

   ```javascript
   const button = document.querySelector("button");
   button.addEventListener("click", () => {
     alert("Button clicked!");
   });
   ```

4. Question: Use the Fetch API or Axios to make a GET request to a URL and log the response.

```javascript
fetch("https://api.example.com/data")
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error("Error:", error));
-0;
```

5. Question: Create a `Person` class with a constructor that takes a name and age as parameters. Add a method that returns a greeting.

   ```javascript
   class Person {
     constructor(name, age) {
       this.name = name;
       this.age = age;
     }
     greet() {
       return `Hello, my name is ${this.name} and I'm ${this.age} years old.`;
     }
   }

   const person = new Person("Alice", 25);
   console.log(person.greet());
   -0;
   ```

6. write a greeting function with Promise, which will get name as param, if the param matched with your name say hello your name, otherwise say the given name is not as expected error.

```javascript
function greeting(name) {
  return new Promise((resolve, reject) => {
    try {
      if (name === "Arun") {
        resolve(`hello ${name}!`);
      } else {
        reject("the given name is not as expected");
      }
    } catch (error) {
      console.log(error);
      reject("something went wrong");
    }
  });
}
-0;
```

7. Array Questions:

- ["3","4","5"] - add 2 element in front of array, "1","2", unshift - 0
- ["1","2","3","4","5"] - remove "5" from the array - 1
  1.push - push element to end,pop- remove element from end of array,shift- remove element front of the array,unshift - add element front of array,

8. Object in javascript:

- how we can find the length of object ? - 0
- how we can use dynamic key to assign values in object
  - example : person = {
    name:"name1"
    }
    assign age to this person using dynamic key.
    person['age']="20"
    person.age="20" - 1

9. what is array.filter, array.map, array.forEach - 1
10. Error handling in javascript method - try{}catch(error){} - 0
11. scopes in javascript: local scope, global scope

example:

```javascript
const user = "Diya";

function getUser() {
  const user = "Deju";
  return user;
}
```

React:

1. What is virtual Dom ? - 1
2. What is JSX ? - 1

- give me sample function component in react

3. what is state in reactjs ? -1

- display name using state.

4. what is props ? - 1

- display greeting using using <Child>, <Parent> component to print Greeting `name`

5. what is difference between componentDidMount() and componentWillUnmount()
6. give sample useEffect() which will get executed function every 5 seconds and with cleanup function.

```javascript
useEffect(() => {
  fetchMessages(); // Initial fetch when the component mounts

  // Simulate real-time updates by fetching messages every 5 seconds
  const interval = setInterval(fetchMessages, 5000);

  // Cleanup function
  return () => {
    clearInterval(interval); // Clear the interval when the component unmounts
  };
}, []);
-0;
```

7. from the users table, you have to show user details based on the user selection from user table,

```javascript
useEffect(() => {
  if (userId) {
    fetch(`https://api.example.com/users/${userId}`)
      .then((response) => response.json())
      .then((data) => setUserData(data));
  }
}, [userId]);
```

8. name some of the hooks concepts in react-hook
   React Hooks provide a way to use state and other React features without writing a class. They are functions that let you "hook into" React state and lifecycle features from function components. Here are some of the common React Hooks concepts:

1. **useState**: Allows you to add state to functional components. It returns a stateful value and a function to update it.

1. **useEffect**: Enables you to perform side effects in functional components. It replaces lifecycle methods like componentDidMount, componentDidUpdate, and componentWillUnmount.

1. **useContext**: Lets you access the context of a parent component without deeply nesting components. It's often used for managing global state.

1. **useReducer**: Similar to useState, but for more complex state logic. It's useful when state transitions follow a specific pattern, like in a finite state machine.

1. **useMemo**: Memoizes the result of a function, preventing unnecessary recalculations in child components when the input data hasn't changed.

1. **useCallback**: Returns a memoized version of the callback function that only changes if one of the dependencies has changed. This is useful to optimize performance in child components.

1. **useRef**: Provides a way to keep references to DOM elements or any other mutable value across renders without causing a re-render when the value changes.

1. **useLayoutEffect**: Similar to useEffect, but it fires synchronously after all DOM mutations. It's often used for measuring DOM elements or performing imperative UI updates.

1. **useImperativeHandle**: Customizes the instance value that is exposed when using the ref attribute with forwardRef.

1. **useDebugValue**: A utility hook that can be used to display a label for custom hooks in React DevTools.

These are some of the core concepts of React Hooks that allow developers to manage state, side effects, context, and performance optimizations within functional components. Keep in mind that the React ecosystem is continuously evolving, so new hooks and concepts might have been introduced since my last knowledge update in September 2021.

- how to get date from child to parent component?, react - is uni-direction and bi-direction?

  Redux:

1. why we need Redux?, is there any pre-defined in react itself ?
2. main concepts in Redux:
   Store: The single source of truth for the application's state. It holds the entire state tree of your application. You can create a Redux store using the createStore function provided by Redux.

Actions: Plain JavaScript objects that describe what happened in your application. They are the only source of information for the store. Actions typically have a type property to indicate the type of action being performed and can also carry additional data.

Reducers: Pure functions that specify how the state changes in response to actions. Each reducer takes the current state and an action and returns a new state. Reducers are combined into a single root reducer using the combineReducers function from Redux.

Dispatch: A method provided by the store that allows you to send actions to the store. Dispatching an action triggers the state change process.

3. how we will map store values to component give me sample code for mapStateToProps?

1. **Define the `mapStateToProps` function**: This function takes the Redux store's state as its parameter and returns an object that maps specific pieces of the state to the props of your component.

```javascript
const mapStateToProps = (state) => {
  return {
    counter: state.counter, // Assuming you have a "counter" property in your Redux state
    user: state.user, // Assuming you have a "user" property in your Redux state
  };
};
-1;
```

2. **Connect your component**: You use the `connect` function from the `react-redux` library to connect your component to the Redux store and map the state to props.

```javascript
import { connect } from "react-redux";

class MyComponent extends React.Component {
  // Your component code
}

// Connect the component to Redux store and map state to props
export default connect(mapStateToProps)(MyComponent);
```

After connecting your component using `connect` and providing the `mapStateToProps` function, your component will receive the `counter` and `user` props, which are mapped from the Redux store's state.

With this setup, whenever the state that `mapStateToProps` depends on changes in the Redux store, your component will automatically re-render with the updated state values.

It's important to note that with the introduction of React Hooks and the `useSelector` hook from the `react-redux` library, using `mapStateToProps` is no longer the only way to connect Redux state to components. You can now also use `useSelector` to achieve similar functionality in a more functional and hook-based way.

3. slice method in redux ? in function component how we will store and retrieve data from using redux hooks ?

- useSelector(), useDispatch()

--- 10, 7,8 selected
--- rejected
