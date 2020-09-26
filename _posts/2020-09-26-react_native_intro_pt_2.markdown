---
layout: post
title:      "React Native Intro Pt. 2"
date:       2020-09-26 15:29:13 -0400
permalink:  react_native_intro_pt_2
---


Hello and welcome back! 

In this blog post we will be continuing from my last blog post, creating a simple Todo App using react native. Let’s dive in! 

So the last thing we did was create a working React Native Application. Now let’s start adding some functionality. The first thing we will do is create some seed data for the application. For this we will be using the state of the application to hold some generic todo’s. To do this we can use class components or use functional components. For this project I used functional components to practice and learn more on something called React Hooks. Just remember you do not need to use React Hooks if you are developing this application with class components. To use state with React hooks you need to import `useState` from react in App.js

`Import React, {useState} from “react”`

In the App function we can use this hook by doing something similar to this: 

```
const [todos, setTodos] = useState([
   { text: "Buy coffee", key: "1" }, 
   { text: "Buy deodarant", key: "2" },
   { text: "Laundry", key: "3" },
   { text: "Learn React Native!", key: "4" },
 ]);
 ```

The “todos” will be used whenever we would like to call the state of the application. All of our todos are stored here. To add or edit the todo we will use the `setTodos`in which takes in a function. More on this will be explained later. 

One thing to note is that in React Native we don’t use html tags like `<div>`, `<span>`... etc. We will use `<View>` and `<Text>` mostly to surround what we would like to render to the screen. `<View>` will be like a `<div>`. Everything we will return from a function will be surrounded by `<View>` instead of a `<div>`. And whatever we would like to render to the screen will be in `<Text>`. To use these components we import them from “react-native”:

`import { View, Text } from “react-native” `

## todoItem.js

Now lets create a new component file named todoItem.js and place this in a new folder named “components” within the primary directory. In this file we will be simply rendering our todos to the screen. This will look like: 
```
import React from "react";
import { Text, View } from "react-native";
export default function TodoItem({ item }) {
 return (
     <View>
        <Text>{item.text}</Text>
     </View>
 );
}
```
In this newly created component we will be receiving a prop called item. We can either use props.item to get this prop or we can deconstruct it like we did above. I deconstructed it because it just looks neater. We see that we are returning a `<Text>` with the contents of the text property of each item, and this is all surrounded by a `<View>`. Simple enough 

Now going back to App.js, we have to import todoItem.js to use the function TodoItem. 

`import TodoItem from "./components/todoItem";`


## FlatList
Now we will introduce another component from react-native called `<FlatList>` so, at this point or imports from react-native looks like this: 

`import { View, Text, FlatList } from “react-native” `

FlatList allows us to go through a list given data and render the data. This data will be our state that we created using the react hook. More information can be found on FlatLists [here](https://reactnative.dev/docs/flatlist.html).

We will be using two properties for FlatList: data and renderItem. data will be equal to our state, or whatever we would like to render. renderItem will be an arrow function, returning what we would like to do with each individual item in the data. Our return in App.js will now look like this: 
```
return (
     <View>
         <FlatList
           data={todos}
           renderItem={({ item }) => (
             <TodoItem item={item}/>
          )}
         />
      </View>
 );
```

In the arrow function we are implicitly returning the TodoItem component in which we imported earlier, with a prop item that is equal to an item. Item is each individual item in the data that is equal to our todos state. 

If you got up to this point, we are now able to see all of our todos on the screen! It looks a little bland now but that’s because we haven’t any styles yet! In my next post I will go over on how to add a new todo to the list. 

Thank you for reading my blog and happy hacking! 

