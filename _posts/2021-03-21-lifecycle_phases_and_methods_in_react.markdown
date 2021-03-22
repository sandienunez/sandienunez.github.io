---
layout: post
title:      "Lifecycle Phases and Methods in React"
date:       2021-03-21 23:52:28 -0400
permalink:  lifecycle_phases_and_methods_in_react
---


## PHASES OF COMPONENTS LIFECYCLE

React components have two sets of properties, props and state. Each react components goes through a complete lifecyle. Components are JS classes that are very fast to react to changes. 

### Initial Rendering Phase: 
Called when the component commences it's lifecycle on it's path to the DOM. 

### Mounting Phase:
Is also known as the creation phase that's called just before it's created. 

### Updating Phase: 
This phase is called after it's created. It's used for any DOM updates following a render. 

### Unmounting Phase: 
This is also known as the cleanup phase since it's called just before it is deleted. It's called once just before it's completely removed from DOM.
 


![logo](https://user-images.githubusercontent.com/61069416/111938449-5aefd680-8aa0-11eb-9c35-36cfa49c98fe.png)
## LIFECYCLE METHODS

Lifecycle methods are called different times in a component's lifecycle. Below are some common methods used in React: 

componentWillMount() – Executed just before rendering takes place both on the client as well as server-side.

componentDidMount() – Executed on the client side only after the first render. Can set up asynch processes (fetching

componentWillReceiveProps() – Invoked as soon as the props are received from the parent class and before another render is called.

shouldComponentUpdate() – Is called just after a component is rendered and updated and called just after rerender has finished. It returns true or false value based on certain conditions.

componentWillUpdate() – Called just before rendering takes place in the DOM.

componentDidUpdate() – Called immediately after rendering takes place.

componentWillUnmount() – Called after the component is unmounted from the DOM. It is used to clear up the memory spaces.



