---
layout: post
title:      "React Redux"
date:       2020-07-05 16:07:09 +0000
permalink:  react_redux
---


We're here! The Final Project. It feels like it was yesterday, working on my first CLI project, but look how far we've come! For my Final Project I decided to create an Application that keeps track of users goals. The user can log what their goals are and maintain a checklist to Reach those goals. Hence, I have named it Reach. 

For this project we used React Redux for our front end development and ol' faithful Rails API for the backend. The backend was more or less the same experience as my previous project. Created two controllers and models with a relationship of: a goal has many todos and a todo belongs to a goal. Two main gems I must highlight here are:

`gem 'active_model_serializers'` 
`gem 'rack-cors'`

The first gem active_model_serializers or AMS is a serializer that I used for association between my goals and todos. This made it much easier for me when communicating with the server, so that when we get one request we get data from both models. For example using a fetch request to GET the goals we would also GET its associated todos. 

The second gem used was rack-cors, this was used so that our application can utilize Cross-Origin Resource Sharing. Essentially this allowed us to access our server from a different server. This is useful since Rails API is running on localhost:3000 and the React Redux front end is running on localhost:3001.

Now on to the React Redux front end of the application. This was my first time working with React Redux and I must say, I do really enjoy it. React is pretty straightforward, create a component, export the component, and import the component where you would like to use it. Redux on the other hand gave me a little trouble. With Redux we introduce something called a store. In addition to having the state within components, we have a mega state called the almighty "Store". This store holds the data we get from our Rails API server, in which we can pass down to our components to render. 

This got a little confusing for me since there are a lot of things to keep track of. What really helped me was installing the Redux Chrome Extension tool. This extension tool was EXTREMELY helpful. It would tell you what the store looks like at any given moment and the state of each component. To install this middle-ware and Thunk(which is used for our Asynchronous actions), I used {compose} from Redux  and implemented the following code: 

```
const composeEnhancers = window.__REDUX_DEVTOOLS_EXTENSION_COMPOSE__ || compose;
const store = createStore(manageGoal, composeEnhancers(applyMiddleware(thunk)))
```


I had the most fun with this project! I got to implement the magic of bootstrap for React within this project too,  and it made it so much more appealing! I am so happy I have made it this far in the course. And I am so excited to see what else I can achieve with these newly learned skills. 


