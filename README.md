## What is React and why it's important

> React is a front-end library introduced by Facebook in 2013 and it has become one of the most popular in the industry.

there are plenty of libraries developed around React, to add features or improve React capabilities in a wide range of areas: routing, state management, server-side rendering, data visualization, styling, mobile development, blogging, testing, etc. There is a React-related library or framework for anything you can imagine, which demonstrates that the adoption of React by the community has been a great success. For these reasons, learning React and its ecosystem is fundamental!

## Virtual DOM

React manipulates the DOM, but DOM manipulation is slow. To solve this problem, React uses a virtual DOM, which is a representation (in memory) of the DOM. React keeps track of the changes in the virtual DOM and updates the actual DOM only as needed, making it really fast.

A virtual DOM object has the same properties as a real DOM object, but it lacks the real thing’s power to directly change what’s on the screen.

Manipulating the DOM is slow. Manipulating the virtual DOM is much faster, because nothing gets drawn onscreen. Think of manipulating the virtual DOM as editing a blueprint, as opposed to moving rooms in an actual house.


