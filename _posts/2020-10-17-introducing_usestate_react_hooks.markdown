---
layout: post
title:      "Introducing useState React Hooks"
date:       2020-10-17 17:27:59 +0000
permalink:  introducing_usestate_react_hooks
---


Hello again! In this article I will be introducing and clearing up some ambiguity of React Hooks. In React you can define components in two ways, Functional Components and Class Components. If you are familiar with Object Oriented Programming, Class components look very similar and seem like the way to go when creating components. Through my time coding in React, I would usually opt in to creating Class Components and only use Functional Components when I'm creating presentational components or “dumb” components. Class Components came with benefits such as state and the use of Lifecycle methods. But with the introduction of React v16.8.0 React hooks became a thing. In a nutshell React hooks allow functional components to hold state and make use of lifecycle methods, such as componentDidMount, componentWillMount, render, etc.. With React hooks Functional Components weren’t considered “dumb” anymore. In this article I will briefly introduce two hooks that can be used in functional components to utilize state and to utilize lifecycle methods. 

## useState

The first hook I will introduce is useState. useState allows functional components to hold state just like class components. In a class component you will normally define the state in the constructor method like so: 

```
constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
  }
	```

Defining the state in the constructor of the class will allow you to create events or alter the state of the component within that class component. In the example above we are initializing the state of the component to count:0. And within our project we can have a different method or an event to alter that state, which will automatically re-render the component. With the introduction of react hooks we are able to use state in functional components, in a similar way. Now you might be asking what exactly is a hook. A simplified definition of a hook is a function that allows you to utilize or “hook into” features of React. 

The first thing we have to do is import useState from react. 

`import React, { useState } from 'react';`

This allows us to call the useState function within our component. When we import the useState function we must then initialize the state that we are using. 

```
function Example() {

 const [count, setCount] = useState(0);
}
```

In the example above we declared a const to `[count, setCount] = useState(0)`. The “count” is going to be the state variable name. So in other words the “count” can be whatever your state is. It could be “name” or “elephants”, you get the point. setCount, is used anytime we would like to change the state of the function. This too coincides with the state variable. So, for best naming practices we usually use the word “set” in front of the state variable name, like “setName” or “setElephant”.

In functional components there is no “this” keyword. This is a big thing for any future React projects you make, and it's also a good interview question too. Since we cannot use “this” we use what we imported earlier, useState. useState takes in one argument and it is whatever we would like to initialize our state variable to. In our example we initialized our state variable count to 0. 

So useState returns a pair, the state variable name (“count”) and a function (“setCount”) that we use to alter the state. 

### Utilization

To read the state, we simply call the name of the state variable. In our case our state variable’s name is “count”

`<span>The count is {count} </span>`

This will render `“The count is 0”`. 

To alter the state we use the function setCount.

`setCount(count + 1)`

Here we are implementing the state variable by 1. 

One thing to note on useState is, if we want to have more than one state variable we would have to declare another useState. So for example we have our first example:

```
function Example() {
 const [count, setCount] = useState(0);
}
```

If we wanted another state variable we would do: 
```
function Example() {
 const [name, setName] = useState(“Alfred”);
 const [count, setCount] = useState(0);
}
```

Unlike class components we declare state variables one at a time. But this doesn’t mean that you must do this all the time. useState can take in an object as well. So it could be something like: 

```
function Example() {
 const [person, setPerson] = useState({
	name: “Alfred”,
	age: 20
});
}
```

This would be depending on what you are coding. You would use best practices to either use an object or two different state variables. 

### Conclusion

In this article I only went over the useState hook. As I mentioned in the intro we can also use hooks in place of lifecycle methods. If you wanted to take a deeper dive into lifecycle methods and how to use them as hooks look up [useEffect](https://reactjs.org/docs/hooks-effect.html) and if you wanted to dive deeper on the useState method check out the documentation React provides [here](https://reactjs.org/docs/hooks-state.html).

React hooks might seem unnecessary if you already know Class Components, and how to use state and lifecycle methods within them. But React hooks are becoming more popular every day. I actually had an interview with a Lead Developer of a major company and he mentioned to me that companies are moving towards the use of React Hooks and functional components. To his point, it makes the code much easier to read for the other engineers you are working with, and it’s more uniform throughout the organization. It also allows you to implement just a few changes to already created functional components, instead of changing the whole functional component to a class component. 

I really hoped this article introduced you to React Hooks and how the React world is shifting towards them instead of Class components. Hope this helped! Happy Hacking! 

