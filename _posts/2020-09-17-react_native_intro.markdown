---
layout: post
title:      "React Native Intro"
date:       2020-09-17 17:42:32 +0000
permalink:  react_native_intro
---


Hello again! After learning React, I wanted to get into building mobile applications. And since I just learned React, React Native was an obvious choice. In this blog post I will be briefly introducing React Native and setting up a simple application called TodoApp from scratch using React Native. Let’s get started! 

### What is React? 

So, before we get started let me explain what exactly is React Native. I won’t get into specifics but I will give you a brief overview of what it is. I would advise you to do your own research by visiting the documentation [here](https://reactnative.dev/).

While we know React is a javascript library, React Native is a framework that utilizes the React library to create mobile applications on both iOS and Android devices. This means that hacking out an application once will allow you to run the application on two different devices without changing any code! I would like to note though that there are some components and properties that are only available to Android users and some that are only available to iOS. 

React Native works very similar to React, using a markdown language called JSX, to build out UIs. But there are key differences that set these two apart. 

One major difference is, React uses  HTML to render the application while React Native does not. For example: Instead of returning a `<div>` in React you will be returning a React Native Component like `<View>`. The use of these React-Native components is to map the real native iOS and Android components on their specific device which allows cross platform development. 

```
import React from "react";
import { View } from "react-native";
 
export default function App() {
 return <View></View>;
}
```


Now to style these React Native Components we will use a Javascript Object that is similar to CSS but not quite CSS. The property used is “style”. The style properties value can be defined inline or more simply by using a StyleSheet. A StyleSheet in React Native is very similar to CSS StyleSheets. One thing to note on styling, for styling properties React Native uses camelCase syntax. 

```
import React from "react";
import { View, StyleSheet } from "react-native";
 
export default function App() {
 return <View style={styles.container}></View>;
}
 
const styles = StyleSheet.create({
 container: {
   flex: 1,
   backgroundColor: "#fff",
   paddingTop: 40,
   paddingHorizontal: 20,
 },
});
```

These are not the only differences between React and React Native. I would advise you to do your own research and find more specific differences. 

### The todo before the Todo:

I will be using a Mac, so if you’re on Windows or Linux commands might be a little different. 

To make sure you can run React Native you must make sure you have npm installed. More information on npm and getting it installed can be found [here](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm).

Now there are two different ways you can create a React Native Application. There is the Expo CLI and the React Native CLI. Expo pretty much is a set of tools that wraps React Native and simplifies development. For example in Expo you easily have access to features like camera or location, but in React Native CLI you have to build these features from scratch. This means that React Native CLI will give you more fine grain control than Expo. Now there are advantages and disadvantages for Expo. But in our case, since this is an introduction and we will eventually be developing a simple Todo application, we will be using Expo CLI. 

To install Expo you will run in terminal: 

```
npm install -g expo-cli

And to create a new project you will run: 

expo init TodoApp
```
 

Now Expo will give you quite a few options to select from when creating an application. These options are broken down into two parts, Managed Workflow and Bare Workflow. For Managed Workflow, Expo will try to manage the complexity of the application, as much as it can manage. But there are limitations. A Bare workflow would be best if you wanted complete control over your application. This is basically the same experience creating a project with React Native CLI. Expo’s website has a great table that is really useful in the comparison between the two. This could be found [here](https://docs.expo.io/introduction/managed-vs-bare/).

In our case we will be using a Managed Workflow. Under Managed Workflow select the first option, “blank”, and hit enter. 

```
? Choose a template: (Use arrow keys)
  ----- Managed workflow -----
❯ blank                 a minimal app as clean as an empty canvas 
  blank (TypeScript)    same as blank but with TypeScript configuration
 
  tabs (TypeScript)     several example screens and tabs using
                        react-navigation and TypeScript 
  ----- Bare workflow -----
  minimal               bare and minimal, just the essentials to get
                        you started 
  minimal (TypeScript)  same as minimal but with TypeScript
                        configuration 
```


When your application has been created cd into the directory and open up your favorite text editor. I use VScode.

So we have the application ready to go but we don’t have anything to view it on. We need emulators. I have provided links to set up both iOS and Android Emulators. These links are really detailed and by far my favorite on the internet. 
[iOS](https://medium.com/@randerson112358/setup-react-native-environment-for-ios-97bf7faadf77)
[Android](https://medium.com/@Charles_Stover/create-a-react-native-app-on-an-android-emulator-1c0d94f288ae)

Now we got everything installed! Run `npm start` in the terminal to make sure everything is working. In the terminal you can hit “i” to start up your iOS application and “a” to start your application on Android. 


### Next Steps: 

If you made it this far we have succsfully created our first React Native Application. It might not look like much but its a start! In next weeks upcoming blog post I will go over how to add functionality in this Todo Application. Until then, Happy Hacking! 




