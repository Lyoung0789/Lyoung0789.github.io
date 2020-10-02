---
layout: post
title:      "React Native Pt.3"
date:       2020-10-02 20:42:04 +0000
permalink:  react_native_pt_3
---


Welcome back! I am guessing that you’ve enjoyed my walk through this far and want to finish up. Well, in this blog we will be developing how to add a Todo to the list that we just created. 

## AddTodo.js
Let’s start off by creating a form where we will type in the new todo. This form will be viewed on the top of the todos. Create a component named addTodo.js and default export a function called AddTodo. 

```
export default function AddTodo() {
return()
}
```

This function is going to need modules from “react-native”. The modules we will need are View, TextInput, and Button.

`import { View, TextInput, Button } from "react-native";`
 

Now like before we are going to surround everything that we want to return in a `<View>` component. Within the view component we are going to have a self closing tag `<TextInput>`. Now TextInput essentially works just like an `<input>` tag in React. Just like React we will have to create a state within AddTodo to hold the value of our input. So lets create a state using our favorite, react hooks. Remember we need to import {useState} from ‘react’

```
export default function AddTodo() {
 	const [text, setText] = useState("");
 
 
 return(
   <View>
	    <TextInput/>
	
  <View>
 )
}
```

TextInput takes a property called onChangeText. OnChangeText will be set to a function we will define called changeHandler. This function will change the state of AddTodo, to whatever we type in the TextInput field. We will also set the placeHolder property to “New Todo” this is just for styling purposes, it's not necessary. 



```
export default function AddTodo({ pressButton }) {
 const [text, setText] = useState("");
 
 const changeHandler = (value) => {
   setText(value);
 };
 
 return(
  <View>
   <TextInput
       placeholder="New Todo"
       onChangeText={changeHandler}
   />
 
 <View>
 )
}
```

Awesome! So now we need to add a Button to actually submit this new todo to the state of App.js. To do this lets go back to App.js and create a function that we need to pass down to AddTodo.js that will add the state of AddTodo to the state of App.js. 

## App.js

Let’s create a function called pressButton that takes in the text state of AddTodo. 
```
const pressButton = (text) => {
   };
```

In this function we are going to change the state of App.js to have the new todo and the todos that were already present before the change. To do this we can use the spread operator. The spread operator is super useful in this situation as it copies the state and simply add the new one to it. I found a super useful blog post that tells you more on the spread operator and in what circumstances you can use it. This can be found [here]( https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab).

```
const pressButton = (text) => {
setTodos((prevTodos) => {
       	return [{ text: text, key: Math.random().toString() }, ...prevTodos];
 
  };
 ```

Now we are going to pass this function as a property to AddTodo. 
```
return (
     <View>    
         <AddTodo pressButton={pressButton} />
     
           <FlatList
             data={todos}
             renderItem={({ item }) => (
               <TodoItem item={item} />
             )}
     </View>
 );
 ```

## Finishing up

Awesome! So now let’s finish up back in the AddTodo.js lets add a button that utilizes the prop we just passed through. We are going to deconstruct the pressButton property when defining the AddTodo function. This is just for cleaner coding. Now add the `<Button>` right under the `<TextInput>`. 
```
import React, { useState } from "react";
import { View, TextInput, Button } from "react-native";
 
export default function AddTodo({ pressButton }) {
 const [text, setText] = useState("");
 
 const changeHandler = (value) => {
   setText(value);
 };
 
 return (
   <View>
     <TextInput
       placeholder="New Todo"
       onChangeText={changeHandler}
     />
 
 
     <Button
       onPress={() => {
         pressButton(text);
       }}
     
     />
   </View>
 );
}
```

Save the application and if you followed everything right you should now have a working application. This application has 0 styling so I would advise to add styling to make things look nice. 

Future Projects
Now that we have a working application there are a couple things you should do. 
First add styling. Styling works a little differently than it does in React I will not be going over this part but Look over `<StyleSheets>`. A great source can be found [here](https://reactnative.dev/docs/stylesheet)

Also there is no back end for this application, so once you restart the application the new todos will disappear. For practice work on a back end portion of the program that can store the information. 

Create a delete button! There's no point in having completed todos in your list if it's already completed. Create a delete button! 

Thank you again for reading my blog! Happy Hacking!

