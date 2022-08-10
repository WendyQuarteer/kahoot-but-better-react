# Kahoot-But-Better-React

- Type of challenge: Mini Project
- Duration: 2 days
- Team challenge : Solo

## The objective
- Consume an API
- Make a React application
- KAHOOT MUSIC INTENSIFIES

## Concretely, what are we going to do?
We are going to try to make a quiz site / application that will be better than Kahoot! Starting with a simple react
project we are going to keep adding layers of complexity 'till we have a super fun quiz to share with friends and family.
Now to make it a bit easier, instead of having the user create their own quizzes we are going to consume the open
trivia database. Here we can fetch multiple choice questions with possible answers! (And the correct one of course ;) )

### Getting started.
1. Know what react is:
   - One of the most popular JavaScript libraries used to build UI on the front-end.  React is all about re-using code.
2. Create a React project in the terminal: ```npx create-react-app kahoot-but-better```
   - index.html(contains a rood div) is inside the public-directory
   - src-directory will contain all the react-code (We only need index.css & index.js)
3. Understand what components are (function components)(class components are no longer needed thanks to hooks): 
(COMPONENTS ARE INDEPENDENT, CUSTOM REUSABLE HTML ELEMENTS like js-functions - DATA IS STORED & HANDLED using props & state)
   - Component-name must start with capital letter.
   - React components implement a render() which can receive a 
     * PROPS: title/input-data via this.props(Stands for properties, arguments passed into components via html-attributes.  
     Props are like function arguments, and you send them into the component as attributes.)
     * STATE: Internal state-data via this.state(The state is a built-in React object that is used to contain data or 
     information about the component. A component's state can change over time; whenever it changes, the component 
     re-renders.)
   - and render it accordingly
   - Components can be referred to inside other components:
```
function Car() {
  return <h2>I am a Car!</h2>;
}

function Garage() {
  return (
    <>
      <h1>Who lives in my Garage?</h1>
      <Car />
    </>
  );
}
```
   - Split each component into separate js-files.
4. Understand what hooks are:
- Hooks rules:
  * Can only be called inside React function components.
  * Can only be called at the top-level of a component.
  * Can't be conditional.
  * It is possible to build a custom hook (not needed for this challenge)
- There are several hooks with each different functionality:
  - useState: to keep track of the application state.  
    * Generally refers to application data or properties that need to be tracked in an application. 
    * RETURNS 2 VALUES: 1st value = current value + 2nd value = a function that updates the state.
    * Create multiple state Hooks to track individual values.
    * Set the initial state to an empty string: useState("").
```
import { useState } from "react";
function FavoriteColor() {
const [color, setColor] = useState("");
}
```
 - useEffect: to perform side-effect in your component.(fetching data, directly updating the Dom, timers,...)
    * 2 ARGUMENTS: 1st value = function + 2nd optional(empty []) = dependency (what the function is dependent on)
    * If there are multiple dependencies, they should be included in the useEffect dependency array.
    * Timeouts, subscriptions, event listeners, and other effects that are no longer needed should be disposed.
Do this by including a return function at the end of the useEffect Hook.
 ```
function Timer() {
const [count, setCount] = useState(0);

useEffect(() => {
let timer = setTimeout(() => {
setCount((count) => count + 1);
}, 1000);

return () => clearTimeout(timer)
}, []);

```
 - useContext: Manage state globally.  It can be used together with the useState Hook to share state between deeply 
nested components more easily than with useState alone. 


   
   
 # kahoot-but-better-react
