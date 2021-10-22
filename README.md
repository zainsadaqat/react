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


