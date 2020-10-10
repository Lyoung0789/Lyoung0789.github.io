---
layout: post
title:      "Using Fetch in JS"
date:       2020-10-10 02:06:34 +0000
permalink:  using_fetch_in_js
---

## Overview
In this blog post I will go over how to use the Fetch API. Let’s start off by giving an overview of what the Fetch API does. 

The Fetch API is used when your web application needs to make network requests to a backend or a remote server, much like an XMLHttpRequest. Fetch API is a newer JavaScript API that is supported by most modern day browsers, and is a much simpler and easier to use than XMLHttpRequests. One of the main differences between these two is that the Fetch API utilizes something called promises. 

## Promises
Promises are defined as objects that represent the completion or failure of an asynchronous call we do using the Fetch API. A promise has three distinct traits. The first state is **Pending**. When a promise is Pending it will transition to either **Fulfilled** or **Rejected**. If the promise becomes Fulfilled the promise will contain the data that we retrieved, and if it is rejected that means the asynchronous call has failed. Now we got promises out of the way let's look at how we actually use the Fetch API. 

## fetch() Method
The fetch() is used to make asynchronous calls to a server. This method takes in one mandatory argument and one optional argument. The mandatory argument is the url that you are requesting from. When you only use the url, the fetch() method will act as a "GET" request. You can check out the HTTP methods [here](https://www.restapitutorial.com/lessons/httpmethods.html#:~:text=The%20primary%20or%20most%2Dcommonly,but%20are%20utilized%20less%20frequently) for an overview. The fetch() method will then return a promise in one of the states we explained earlier. If the promise is Fulfilled the promise returns a Response object in which we can use the .then() function to proceed with the response of the asynchronous call. If the promise is Rejected we can use the .catch() function to handle the Error object. So a basic function would look something like this

```
fetch(url)
.then(response => {
//do something with the response
}
.cach(error =>{
//error handling
}
```

## The Response Object
When we make a fetch request to a server, and it is Fulfilled, we get a Response object. This Response object has a bunch more data than what you are requesting. To get the data that you need you need to use a method called .json(). This method takes the response, reads and parses it and returns another promise. The returned promise has the data that we are looking for. The key to this is that it returns a promise. So we will use another .then function to do what we want with the data. Now the JavaScript code will look like: 

```
fetch(url)
.then(response => {
return response.json()
}
.then(data => {
//do what we want with the data
}
.catch(error => {
//error handling
}
```

We have successfully used the fetch() method to "GET" data from a server! Just a note, we use .then() methods because we are making asynchronous calls. This means that whenever we get a promise we will immediately do whatever the .then() method calls. This allows the rest of the program to function normally while we are requesting and parsing the data from the promises. Once we get the promise we “then” continue working on what we were doing with it. 

## Optional Argument
As I mentioned before there is an optional argument that the fetch() method takes. This optional argument is an object with certain keys. The below snippet is taken from [here](https://github.github.io/fetch/).

**Options**</br>
method (String) - HTTP request method. Default: "GET" </br>
body (String, body types) - HTTP request body</br>
headers (Object, Headers) - Default: {}</br>
credentials (String) - Authentication credentials mode. Default: "omit"</br>
"omit" - don't include authentication credentials (e.g. cookies) in the request</br>
"same-origin" - include credentials in requests to the same site</br>
"include" - include credentials in requests to all sites</br>


Notice that when we make a fetch request without the optional argument we are really doing a “GET” request because the optional method is “GET” by default. 

If we wanted to do a “POST” request (uploading JSON data) our fetch() method will look something like this: 
```
fetch(url, { 
method: 'POST', 
headers: { 'Content-Type': 'application/json', }, 
body: JSON.stringify(data), }
)
```

"data" in the above example is the data you are uploading to the server. We use JSON.stringify() so that it converts data into JSON. The fetch will still return a response in one of the three states. If it is Fullfilled, the promise will return the data that was submitted. A full "POST" request to a server will look something like: 

```
fetch(url, { 
method: 'POST', 
headers: { 'Content-Type': 'application/json', }, 
body: JSON.stringify(data), }
)
.then(response=>{
return response.json()
}
.then(data => {
//do something with the data 
}
.catch(error => {
//do something with error
}
```

And there you have it! This is how you use the Fetch API in a Javascript application. I hope this was helpful!




 



