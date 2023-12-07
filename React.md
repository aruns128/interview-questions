1. demonstrate controlled and uncontrolled input components using hooks.

Controlled Input Example:

```jsx
import React, { useState } from "react";

function ControlledInput() {
  const [inputValue, setInputValue] = useState("");

  const handleInputChange = (e) => {
    setInputValue(e.target.value);
  };

  return (
    <div>
      <input type="text" value={inputValue} onChange={handleInputChange} />
      <p>Value: {inputValue}</p>
    </div>
  );
}

export default ControlledInput;
```

Uncontrolled Input Example:

```jsx
import React, { useRef } from "react";

function UncontrolledInput() {
  const inputRef = useRef();

  const handleButtonClick = () => {
    alert("Input Value: " + inputRef.current.value);
  };

  return (
    <div>
      <input type="text" ref={inputRef} />
      <button onClick={handleButtonClick}>Get Value</button>
    </div>
  );
}

export default UncontrolledInput;
```

## Create a React component called UserList that fetches data from the JSONPlaceholder API (https://jsonplaceholder.typicode.com/users) and displays a list of user names. Explain how you would ensure that the API request is made when the component mounts, and how you handle any potential errors during the API call.

```jsx
import React, { useState, useEffect } from "react";
import axios from "axios";

function UserList() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    // Make a GET request to the JSONPlaceholder API
    axios
      .get("https://jsonplaceholder.typicode.com/users")
      .then((response) => {
        // Set the retrieved data in the state
        setUsers(response.data);
      })
      .catch((error) => {
        console.error("Error fetching data:", error);
      });
  }, []); // The empty array [] ensures this effect runs once, like componentDidMount

  return (
    <div>
      <h2>User List</h2>
      <ul>
        {users.map((user) => (
          <li key={user.id}>{user.name}</li>
        ))}
      </ul>
    </div>
  );
}

export default UserList;
```

React Problem
Fetch and render data in some card from dummy api
https://api.thecatapi.com/v1/images/search?limit=5&page=10&order=Desc

     Easy: Fetch data on some button click and render it.

Should handle loading state
Should handle empty state and error state
Emphasis on creating a grid layout of cards

React Problem 3: Create a stopwatch component

Pause
Resume
Stop
Init

Q. React Problem 2: Create an Autocomplete component

Asynchronous
Debounce
List rendering

---

# theory question

1. why cant browser read JSX?

Browsers can't directly read JSX (JavaScript XML) because JSX is not a natively supported part of the JavaScript language. JSX is a syntax extension for JavaScript that is commonly used with libraries like React. It is not a standard JavaScript feature like variables, loops, or functions.

Here's why browsers can't read JSX directly:

1. **JSX is Transpiled:** JSX needs to be transpiled into standard JavaScript code before it can be executed in a browser. Transpilation is the process of converting JSX code into plain JavaScript. Tools like Babel are commonly used to perform this transformation. Browsers can execute JavaScript, not JSX.

2. **React and Libraries:** JSX is primarily associated with React, a popular JavaScript library for building user interfaces. React provides the necessary runtime to interpret and render JSX components. It's React, not the browser, that reads and renders JSX.

3. **Complex Features:** JSX often includes features and constructs that are not natively understood by browsers. For example, it may contain custom React components, which are not part of standard JavaScript.

Here's a simple example of JSX code and how it gets transpiled into JavaScript:

```jsx
// JSX
const element = <h1>Hello, JSX!</h1>;

// Transpiled JavaScript
const element = React.createElement("h1", null, "Hello, JSX!");
```

In the transpiled code, `React.createElement` is a function provided by the React library to create a virtual DOM element, which can be rendered in the browser.

To work with JSX in a browser, you need to include the transpiled JavaScript code, along with the React library, in your web application. This code is then executed in the browser to render the JSX components. The browser itself does not understand JSX directly; it relies on JavaScript and libraries like React to handle it.
