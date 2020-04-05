---
layout: post
title:      "Sinatra - WorkOut Application"
date:       2020-04-05 19:29:04 +0000
permalink:  sinatra_-_workout_application
---


During these times of being stuck at home due to the pandemic, we can easily get into a routine of siting on the couch and watching Netflix all day. But to stay healthy we need to be active! Since all the gyms are closed, why not work out at home! The idea for this app came to me when I was siting on my bed eating some salt and vinegar chips, feeling really crappy about myself. So I thought it would be great if I can create something, so that when I do work out I can keep track of my exercises for the day. 

The creation of this application was pretty tough. It combined basic procedural Ruby, with ActiveRecord and the Sinatra framework. The most difficult part for me was following the Restful routes. Restful routes are pretty much a standard among HTTP verbs and CRUD actions. It follows certain principles everyone follows to prevent confusion among the structure of web creation. The routes the actions that the user takes can be very difficult to understand, but after a BUNCH of trial and error, I figured out how to successfully navigate Restful routes. 

Another issue I had to overcome was not letting the logged in user alter data that doesn’t belong to them. In this project I used the relationship: User has many exercises and an exercise belongs to a User. I was able to use CRUD (Create, Read, Update, Delete) for the exercises, so that a User can edit their own exercises. I had to place logical statements within the controllers so that it would check the current_user was the same as the user that is associated with the exercises user. If they were not the same, this would mean that there was some shady stuff going on with the logged in user. In this case, I would redirect that user to the login screen or back to their homepage, without altering any of the data, they just attempted to edit. 

Overall, I learned so much with this project! Everything I learned up to this point I utilized. So if I can give any new student advice… Keep up with the lessons! Everything we learn is like a new building block to the bigger picture. And not knowing how to build just one block can cause your building to come crashing down. 

I hope you enjoyed this project as much as I did!!

