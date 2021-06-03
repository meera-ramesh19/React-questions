# React-questions

# 1.What is React.js?

```
  
React.js is declarative
React.js is simple
React.js is component based
React.js supports server side
React.js is extensive
React.js is fast 
React.js is easy to learn 
React makes it painless to create interactive UIs. Design simple views for each state in your application, and React will efficiently update and render just the right           components when your data changes.


```

---

# 2. Why would you use React.js?



```      
 Simplicity
 Developers love it
 Reusable elements
 Easy to update components, individually or in bulk
 Virtual DOM
 React Native and Mobile Apps

```

---


# 3. What are components?


```

Components are like functions that return HTML elements.
Components are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and return HTML via a render() function.
Components come in two types, Class components and Function components, in this tutorial we will concentrate on Class components.


```


---


# 4. What ia JSX?


```
JSX is an extension of the JavaScript language based on ES6, and is translated into regular JavaScript at runtime.
JSX is an XML/HTML-like syntax used by React that extends ECMAScript so that XML/HTML-like text can co-exist with JavaScript/React code.
By using JSX you can write HTML-like structures in the same file as you write JavaScript code.
It is faster than normal JavaScript as it performs optimizations while translating to regular JavaScript.
It makes it easier for us to create templates.
Instead of separating the markup and logic in separated files, React uses components for this purpose. We will learn about components in detail in further articles.
JSX is basically a syntax extension of regular JavaScript and is used to create React elements. These elements are then rendered to the React DOM


```

---


# 5. What are props?


```

Props is short for properties and they are used to pass data between React components. React’s data flow between components is uni-directional (from parent to child only).
React Props are like function arguments in JavaScript and attributes in HTML.To send props into a component, use the same syntax as HTML attributes.
Props are also how you pass data from one component to another, as parameters.
Props  are immutable.  The React philosophy is that props should not change, parent components can send prop values to child components but the child cannot modify its own props. Components that use only props will always render the same output when given the same input and this makes them easier to test.
```

---




# 6. What is State?


```

State is a JavaScript object that stores component’s dynamic data and it enables a component to keep track of changes between renders.state is dynamic, it is reserved only for interactivity .
State is an object that represents the parts of the app that can change.
State is an instance of React Component Class can be defined as an object of a set of observable properties that control the behavior of the component



```

---


# 7. What are React Hooks?


```

Hooks are a new addition in React 16.8. They let you use state and other React features without writing a class.
React Hooks are functions that let us hook into the React state and lifecycle features from function components
Hooks allow us to easily manipulate the state of our functional component without needing to convert them into class components
Hooks let you use the functions instead of switching between HOCs, Classes, and functions.


```
---

# 8. What are React Hooks?


```



In React with every render, the function being rendered is a new one – how does the ‘state’ persist then? Behind the scenes, there’s an object representing the functional component in the memory, which has a stack of its own. Whenever the useState() hook is used, the value of the state variable is changed and the new variable is stored in a new cell in the stack. The stack pointer is incremented simultaneously to point towards the last cell. The value pointed to by this stack pointer is used after every render. On a deliberate refresh from the user, the stack is dumped, and a fresh allocation in the memory is done when the component is rendered. 



```
---


# 9. Give an example of useState?


```
**Example1**: Updating state based on previous state (useState with a number)
Let’s look at another example: updating the value of state based on the previous value.

This eacmple will tell you how many steps you took at the press of a button

import React, { useState } from 'react';

function StepTracker() {
  const [steps, setSteps] = useState(0);

  function increment() {
    setSteps(prevState => prevState + 1);
  }

  return (
    <div>
      Today you've taken {steps} steps!
      <br />
      <button onClick={increment}>
        I took another step
      </button>
    </div>
  );
}

ReactDOM.render(
  <StepTracker />,
  document.querySelector('#root')
);
First, we’re creating a new piece of state by calling useState, initializing it to 0. It returns an array containing that initial value, along with a function for updating it. We’re destructuring that into variables called steps and setSteps. We also wrote an increment function to increase the step counter.

You’ll notice we’re using the functional or “updater” form of setSteps here. We’re passing a function instead of a value.

React will call that updater function with the previous value of the state, and whatever you return will replace the state with a new value. The argument is called prevState in the example but you can name it anything.

We could just call setSteps(steps + 1) and it would work the same in this example… but I wanted to show you the updater form, because it’ll be useful in case your update is happening in a closure which has captured a stale value of the state.

Another thing we’ve done here is write a standalone increment function, instead of inlining the arrow function on the button’s onClick prop. We could have written button this way and it would’ve worked just the same:

<button onClick={() => setSteps(prevState => prevState + 1)}>
  I took another step
</button>

**Example 2: **
Simple UseState examples
In order to use the hook useState , you will have to import it from the React package first.
Here is an example:
import React, { useState } from 'react'
Now you can start using the hook on your code without any problems. Have a look at the example below:
import React, { useState } from 'react'

function Component() {
  const [name, setName] = useState('Mehdi')
}
Notice that we are using the ES6 array destructuring inside the component. So the variable name inside the array refers to the argument of the function useState (current state). On the other hand, the variable setName refers to the function that you will add to update the state. So this means we have a state named name and we can update it by calling on setName() function.
Let’s use it on the return statement:
import React, { useState } from 'react'

function Component() {
  const [name, setName] = useState('Brad')

  return <h1> My name is {name} </h1>
}
//Returns: My name is Brad
Since function components don’t have the setState() function, you need to use the setName() function to update it. Here’s how you change the name from “Brad” to “John”:


```

---


# 10. What are the differences between functional and class based components and give an example of funcitonal and class based components?


```
 The clear difference between functional and class based components is the syntax. Just like in their names, a functional component is just a plain JavaScript function that returns JSX. A class component is a JavaScript class that extends React
Functional components are some of the more common components that will come across while working in React. These are simply JavaScript functions. We can create a functional component to React by writing a JavaScript function.

Syntax:

const Car=()=> {
  return <h2>Hi, I am also a Car!</h2>;
}

Passing props in functional component:Inside a functional component, we are passing props as an argument of the function. Note that we are using destructuring here.
const FunctionalComponent = (props) => {
 return <h1>Hello, {props.name}</h1>;
};


using state in functional components:To use state variables in a functional component, we need to use useState Hook, which takes an argument of initial state. In this case we start with 0 clicks so the initial state of count will be 0. useState returns the current state and a function that updates it, we are destructuring the array.


const FunctionalComponent = () => {
 const [count, setCount] = React.useState(0);

 return (
   <div>
     <p>count: {count}</p>
     <button onClick={() => setCount(count + 1)}>Click</button>
   </div>
 );
};

Class Component: .Component which has a render method.This is the bread and butter of most modern web apps built in ReactJS. These components are simple classes (made up of multiple functions that add functionality to the application).when defining a class component, you have to make a class that extends React.Component. The JSX to render will be returned inside the render method.



Syntax:

class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}

Passing Props in Class component:Since it is a class, you need to use this to refer to props. And of course, we can use destructuring to get name inside props while utilizing class-based components.

class ClassComponent extends React.Component {
  render() {
    const { name } = this.props;
    return <h1>Hello, { name }</h1>;
 }
}


useState in Class component: Inside the constructor, you will make a state object with a state key and initial value. And inside JSX, we use this.state.count to access the value of the state key we defined in the  constructor to display the count. Setter is pretty much the same, just different syntax.



class ClassComponent extends React.Component {
 constructor(props) {
   super(props);
   this.state = {
     count: 0
   };
 }

 render() {
   return (
     <div>
       <p>count: {this.state.count} times</p>
       <button onClick={() => this.setState({ count: this.state.count + 1 })}>
         Click
       </button>
     </div>
   );
 }
}

Alternatively, you can write an onClick function. Remember, the setState function takes argument(s) of state, props(optional) if needed.

onClick={() =>
  this.setState((state) => {
    return { count: state.count + 1 };
  })
}


```

---
