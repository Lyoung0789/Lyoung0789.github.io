---
layout: post
title:      "Axios in React"
date:       2020-10-31 14:04:35 -0400
permalink:  axios_in_react
---


If you read my past blog post on using the Fetch API you will be somewhat familiar with http requests. I would like to introduce a different way to proccess http requests called Axios. In my experience when I was introduced to Axios, it made my http requests so much easier to understand and so much easier to implement in applications. In this blog post I will go over how to use Axios using `GET`,` POST`, and `DELETE`. Also go over some features that make it different from using fetch.


Axios is a promise based HTTP client for the browser and node.js. From the browser it makes XMLHttpRequests and from node.js makes http requests. You are able to intercept, transform, and cancel requests while protecting against XSRF(cross-site request forgery). One major thing that I enjoy about Axios is the functionality of automatically transforming JSON data. Let’s dive into how you can use Axios in your React application. 

## Installing Axios
First thing we need to do is install Axios.
If you are using npm:

`npm install axios`

If you are using yarn: 

`yarn add axios`


When using Axios in React you must always remember to import it in the component you are using it in. 

`import axios from ‘axios’`

## GET Request
In this example I will be using a free api to send my requests too. I will provide some code if you would like to reference, but when reading this you should know the fundamentals of React. I made a component called Testing.js for you to follow along. 

```
import React from 'react';
import axios from 'axios'
 
const Testing = () => {
    const handleClick = () =>{
        axios.get("https://reqres.in/api/users?page=2")
        .then(response => {
            console.log(response.data)
        })
    }
 
    return(
        <div>
            <button onClick={handleClick}>Fetch Data</button>
        </div>
    )
}
 
export default Testing
```
In this component, I created a simple button that sends a `GET` request to “https://reqres.in/api/users?page=2” which is a free api. This can be changed to wherever your api is located. In `handleClick()` we use:

`axios.get(url[, config])`

This returns a promise in which we then pull out the data and console log it to the screen. Within the `.then()` you notice something a little different. In Fetch we would have to convert the data to JSON before we are able to console log it. Like so: 
```
fetch('https://reqres.in/api/users?page=2')
  .then(response => response.json())    // this is an additional step
  .then(data => {
    console.log(data) 
  })
```
But as I mentioned before Axios automatically converts the data in JSON for us! So there’s no need for that additional step!

## POST
For this `POST` example I am using a class component called `Testing.js`. I coded out a simple form for users to input their email, first name, and last name to post to the api.
```
import React, {Component} from 'react';
import axios from 'axios'
 
 
class Testing extends Component {
 
    state = {
        email: "", 
        firstName: "", 
        lastName: "",
    }
 
    
    handleChange = (event) => {
        this.setState({
            [event.target.name]: event.target.value
        })
    }
 
    handleSubmit = (event) =>{
        event.preventDefault()
        const {email, firstName, lastName} = this.state
        axios.post("https://reqres.in/api/users?page=2", {email, firstName, lastName})
        .then(response => {
            console.log(response)
            console.log(response.data)
        })
    }
 
    render(){
        return(
            <form onSubmit={this.handleSubmit}>
            <input type="email" name="email" value={this.state.email} placeholder = "Email" onChange={this.handleChange}/>
            <input type="text" name="firstName" value={this.state.firstname} placeholder="First Name" onChange={this.handleChange}/>
            <input type="text"  name="lastName" value={this.state.lastName} placeholder="Last Name" onChange={this.handleChange}/>
            <button type="submit">POST</button>
           </form>
        )
    }
}
 
export default Testing
```
In the handleSubmit method I used `axios.post(url[, data[, config]])`. The url is the api we are trying to POST to and the data is what we are posting. One thing to note is that data will always be an object. I used destructuring to pull out the state and passed it into `axios.post()` as an object. I then used a `.then()` to console log the response from the api. In my case I got back a status: 201, which means created. 


## DELETE
For this `DELETE` example I used a class component, and a form where the user would input the ID of the user they would like to delete. 
```
import React, {Component} from 'react';
import axios from 'axios'
 
 
class Testing extends Component {
 
    state = {
        id: ""
    }
 
    
    handleChange = (event) => {
        this.setState({
            [event.target.name]: event.target.value
        })
    }
 
    handleSubmit = (event) =>{
        event.preventDefault()
        const {id} = this.state
        axios.delete(`https://reqres.in/api/users/${id}`)
        .then(response => {
            console.log(response)
        })
    }
 
    render(){
        return(
            <form onSubmit={this.handleSubmit}>
            <input type="text" name="id" value={this.state.id} placeholder = "ID" onChange={this.handleChange}/>
            <button type="submit">DELETE</button>
           </form>
        )
    }
}
 
export default Testing
```

I used the `axios.delete(url[, config])` to remove a user from the api. Make sure to change the url according to which user you would like to delete. In the `.then()` I console logged the response from the server, in which I got a `status: 204`. Which means that it has been deleted.

## Conclusion
So there you have it! That’s how to use Axios with `GET`,` POST`, and `DELETE` http requests. If you would like to review more on Axios their github page is really informative. It could be found [here](https://github.com/axios/axios). 

I hope you enjoyed this blog! Happy Hacking!

