## What is React and why it's important

React is a front-end library introduced by Facebook in 2013 and it has become one of the most popular in the industry.

there are plenty of libraries developed around React, to add features or improve React capabilities in a wide range of areas: routing, state management, server-side rendering, data visualization, styling, mobile development, blogging, testing, etc. There is a React-related library or framework for anything you can imagine, which demonstrates that the adoption of React by the community has been a great success. For these reasons, learning React and its ecosystem is fundamental!

## Virtual DOM

React manipulates the DOM, but DOM manipulation is slow. To solve this problem, React uses a virtual DOM, which is a representation (in memory) of the DOM. React keeps track of the changes in the virtual DOM and updates the actual DOM only as needed, making it really fast.

A virtual DOM object has the same properties as a real DOM object, but it lacks the real thing’s power to directly change what’s on the screen.

Manipulating the DOM is slow. Manipulating the virtual DOM is much faster, because nothing gets drawn onscreen. Think of manipulating the virtual DOM as editing a blueprint, as opposed to moving rooms in an actual house.

## Why are React components important?

Components are at the heart of React. They are pieces of code with a specific purpose, that you can reuse and compose to build bigger, complex applications (yes, just like functions!). The idea of components is not exclusive to React. Almost every library or framework has components, and sometimes you will hear the concept of modules or widgets - the name is different, but the idea is the same: to make code reusable.

## Why are React state and props important?

As you already learned in the components lesson of this module, React components can have state and props. Now let's go deeper and see how they work. State and props are the two ways React can update a component or share data between components. They are the key to compose a complex application using several components. When props or state changes, React will re-render the parts of your application that use this data, keeping it up-to-date.

## Props

A React application is not composed of a single (and huge) component. Even if it's technically possible, is not practical. React is a component-based library and it expects you to break the UI into a component hierarchy. In other words, you may have a root component, and it will have children. You can pass data from parent to children using props (like passing arguments to a function).

## Handling events

JavaScript has different kinds of events: browser events (load, unload, scroll, etc.), mouse events (click, double click), keyboard events (key down/up), form events (submit), HTML element events, and even CSS events.

## Lifecycle methods

Every phase of the lifecycle of a component has its own methods. Sometimes a method is available in more than one phase.

1. Mounting (putting elements in the DOM):

`constructor()`
`getDerivedStateFromProps()`
`render()` (mandatory)
`componentDidMount()`

2. Updating (props or state changes):

`getDerivedStateFromProps()`
`shouldComponentUpdate()`
`render() (mandatory)`
`getSnapshotBeforeUpdate()`
`componentDidUpdate()`

3. Unmounting (element is removed from the DOM):

`componentWillUnmount()`


## React and Redux (with Hooks)

Termonologies used is redux:

`Action` `Action Creator` `Action Type` `Action Payload` `Dispatch` `Reducer` `Store`

Redux Data Flow 

`UI -> Action Creator -> Action Type and Action Payload -> Dispatch - > Reducer -> Store -> Updated UI`

> Let's dive into it

`npx create-react-app react-with-redux --template redux` // use `--template redux` only if you're comfortable with redux

now we need to install few dependencies 

`npm install redux react-redux`

### Steps

1. Create Reducers ( a function that takes two parameters (state, action)

2. Combine all reducers ( combine all the reducers as a root )

3. Create a store ( store uses that combined reducer and passed as a parameter, createStore(reducers)

> Now, we need to hook up that store with our React application but first we need to make our store available for all our components.
> for this, we need to wrap our App component with Provider component

To Access data in the store, we use useSelector hook

4. Access data from store useSelector((state) => state)

5. Create action creators to update our stores ( Action creator is just a function that dispatches an action )

6. useDispatch is using asynchronous code and To help redux use asynchronous code , we use redux-thunk library `npm install redux-thunk`

## React Hooks

### useState Hook
Hooks only work inside of functional components and we can't put hooks inside of any block or nest them. it must be on the top level of functional component.
```
const Hooks = () => {
const [count, setCount] = useState();
count is the state of Hooks Component and setCount is a function that's used to update the value of count state. Each time state value changes. It re-renders the whole component with the new value of count.

const decrementCount = () => {
  setCount((prev) => prev - 1)
}

const incrementCount = () => {
  setCount((prev) => prev + 1)
}

return (
  <>
    <button type="button">-</button>
    <span>{count}</span>
    <button type="button">+</button>
  </>
  )
}
```

### useEffect Hook

**Syntax:** useEffect(function, dependency)

```
import { useState, useEffect } from 'react'
  
const [count, setCount] = useState(0);

useEffect(() => {
  setTimeout(() => {
    setCount(prev => prev + 1)
  }, 1000)
}) // useEffect without any dependency array runs after each render
```

#### 1. No dependency passed:

```
useEffect(() => {
  //Runs on every render
});
```

#### 2. An empty array:

```
useEffect(() => {
  //Runs only on the first render
}, []);
```

#### 3. Props or state values:

```
useEffect(() => {
  //Runs on the first render
  //And any time any dependency value changes
}, [prop, state]);
```

### useContext Hook

It can be used together with the useState Hook to share state between deeply nested components more easily than with useState alone.

```
import {useState, createContext, useContext} from 'react';

const UserContext = createContext();

const Component1 = () => <UserContext.Provider value="Hey Prop"><Component2 /></>
const Component2 = () => <><Component3 /></>
const Component3 = () => <><Component4 /></>
const Component4 = () => {
user = useContext(UserContext)
return (
  <h2>User: {user} </h2>
)
}

```
  
## Redux

### Complex Reducers

```
initialState = { favoriteRecipes: [], allRecipes: [], search: '' }

const reducer = (state = initialState, action) => {
  switch(action.type) {
    case 'favoriteRecipe':
      return { ...state, favoriteRecipes: [...state, action.payload] }
    case 'addRecipe':
      return {...state, allRecipes: [ ...state.allRecipes, action.payload ]}
    case 'toogleRecipe':
      return {...state, allRecipes: state.allRecipes.map(recipe => {
        return (recipe.id === action.payload.id) ? {...recipe, completed: !recipe.completed} : recipe;
      })
    default:
      return state;
  }
}
```







