Video [Link](https://youtu.be/uE925hp9KDk?si=kBKaSswSUWpGGuZm)

## Hooks
##### What is Hooks 
- A hook is a special function that let developer to "hook into" react state and lifecycle feature from a functional component without need for writing a class component
- Hooks can be only implemented inside the functional component
##### Why we need hook
- This enables developers to access the react state and lifecycle features inside the function component more precisely compared to the class component.
##### How hook works

##### useState
What is a State : The state is **a built-in React object that is used to contain data or information about the component**

It enables the declaration of state variable and provides us a function  to update it, every time it is updated, triggers re render of the component
- Widely used one and very important one

```Js
import React, {useState} from 'react';
function demo(){
	const [number,setNumber] = useState(0);
	const incrementNumber = () => {
		setNumber(prevNumber => prevNumber+1);
	}
	return (
		<p>Count : {number}</p>
		<button onclick={incrementNumber}>Click to Update</button>
	);
}
```
#### useEffect 

This allows to perform side effect in our component, allowing our code to synchronize with the external system
Side effect Ex : fetching of data, Timers, connection with db

When component renders starts, the useEffect will run once, and When every there is a change in our dependencies ( we will pass while writing useEffect ) , the code inside useEffect will get executed
- If there is no dependencies, **it will execute the effect after every render of the component**
- We can also set timer, so we can control how often code inside it runs.
- The return keyword can be used in useEffect, that getting executed when we close the component
```Js
import {useState,useEffect} from "react";

function IncreamentingNumber(){
	const [number,setNumber] = useState(0);
	
	useEffect(()=>{
		const timer = setTimeout(()=>{
			setNumber(number+1);
		},1000)
		
		return () => clearTimeout(timer)
	},[number])
	
	return <p>{number}</p>
	
}
```

#### useContext
`useContext` is a way to manage and share state globally across components in a React application. It is often used alongside `useState` or other state management hooks to make a state variable accessible to multiple components, without the need for prop drilling.
##### When to use `useContext`

Consider a situation where you need to pass a state variable from a parent component to a deeply nested child component. If the nesting level is shallow, you can simply use props to pass the data. This technique is known as **prop drilling**.

However, if the component tree is deeply nested, passing props through many intermediate components becomes inefficient and hard to manage. It can also affect the performance and readability of the application.

To solve this, **`useContext`** can be used to avoid prop drilling by providing a way to share values directly with any component in the tree, no matter how deeply nested it is.

##### Example At [Chatgpt](https://chatgpt.com/c/6824c9ac-3000-8007-8820-0b5f204b7787)

#### useReducer
`useReducer` is similar to `useState` and provides an alternative for managing state within a React component, particularly when dealing with multiple state variables and their associated types and update logic.

It's a powerful tool for managing more intricate state transitions in a predictable and organized way.


#### useMemo

The `useMemo` hook is used to **memoize** the result of a computation, meaning it caches the result and returns the cached value

Memoization is similar to caching — it stores the result of a function call and returns the stored result when the same inputs occur again.

the `useHook` only runs when it's dependencies are updated, which increases the performance

In simple terms, `useMemo` is a React Hook that lets you **cache the result of a computation between renders**, only recalculating the value when one of its dependencies has changed.
#### useCallback

#### useRef

`useRef` let us create a reference variable to a value or a DOM element that you can keep around without triggering a re-render when it changes

It directly access the DOM

-> Updating `useRef` values don't cause re-render
-> `useRef` is differ from `useState`, as `useState` is used when we want to update the UI on the change of value
-> Storing mutable values that shouldn’t trigger re-renders

## Higher order components

- What is, when to use, Why we use, How do we use
##### What is 
Higher order component is a function that takes a component and return a new component with enhanced functionalities, it is similar to Higher order functionality which take another function as argument and returns new function

HOCs are used to share common logic between component that are similar but not identical
##### When to use
- When you share same logic but between components
	Ex : Authentication, Logging, Analytics
- Adding props or modifying behavior
	Ex : Adding a console log before the component renderings
##### How do we use and examples

###### Create a HOC
```Js
import react from 'react';

function WithGreet(WrappedComponent){

	return function EnhancedComponent(props){
		return
		<div>
			<p>Hello!</p>
			<WrappedComponent {...props}
		</div>
	}
}

export default WithGreet;
```

###### Creating a Child component
```Js
import react from 'react';

function User({name}){
	return <p> User : {name} </p?
}

export default User;
```

###### Wrapping component with HOC
```Js
import react from 'react';
import User from './user';
import WithGreeting from './WithGreeting'

const GreetUser = WithGreeting(User);

function App(){
	return 
	<GreetUser name={"myname"} />
}

```

## Life cycle methods of components
Learn the concepts of 
- How Call Components
- 3 Phases -> mounting -> updating -> unmounting

There are three phases 
- **Mounting** : Initializations, renders, and mounts the component 
- **Updating** : Handles state/props changes, re-renders, and updates
- **Unmounting** : Cleans up before removal

#### Mounting
This refers to process of creating and inserting component into DOM for first time in the application
During this process, 
- React initiates component
- set the internal state 
- and insert into DOM

##### Functions

###### constructors()
method to initialize state and binding methods
###### getDerivedStateFromProps(prop, state)
Used to update the state based on the props, this get executed before every render
###### render() method
responsible for rendering JSX and updating DOM

###### componentDidMount() function
This is invoked right after component is fit into the DOM, this function get called after render function is executed first time.

## State management

#### What is  state/props

**State** is managed within the component, similar to declaring a variable inside the function.
It is used to store the data or function that can be changed over time and that is specific for the component.

**Props** ( Properties ) are passed to a component from a parent component similar to passing parameters or arguments to a function.
They are immutable inside the passed function that means you can't change the values.
When parent update the value of the prop, the child component is also re-rendered
#### What is props drilling

Prop drilling refers to a process of passing data down through multiple level of nested components.
Even some times the intermediate component don't use the data, but they receive to pass it to the destinated child component.

**This lead to several problems :**

- The components become more tight coupled
- Maintenance is harder
- Increase the complexity in reading the code

**Solution for these problems :**

 - Context API : allow to access data from a shared context without passing it.
 - Using of state management libraries
#### What is react context

This is way to share the data among components without prop drilling.
This is used for the data that is more needed to many components
While this is convenient for sharing data, It's always not the best solution.
#### How data is passed between two siblings


## Virtual Dom
#### What is Virtual DOM

- Reconsoliation
- React Fibre
- Diffing algorithm
- renders ( How works )

## Redux
Learn
- How it works
- Why we need
- when we need
- redux tool kit (RTK)

## Custom Hooks
- When to use
- Learn to code ( For local storage )

## SSR vs CSR
- What is both
- Diff
- SEO on SSR
- performance

## Routing (Role Based Access Control)
- React routes
- How will you protect your routes
- Dynamic Routing
- How will you handle routing
- How will you handle queries and parameter

## React testing

- Know about react testing
- Know about writing test cases
- Know about unit testing, Component testing

## Async tasks ( learn in depth )

- API Calls
- Events
- Promises (must know)

## Re-usability / Modularity / Testability

- Learn to code with these
- This is not question but on coding round focus to write code with these

## Performance

- Lazy loading
- Asset optimization
- How to optimize JS, CSS, Code
- Bundler

## Styling

- Learn about tailwind, styleX, Bootstrap, material UI
## Accessibility
## Security


## Lazy loading ( very imp )
- code splitting
- code chunking
- suspence
