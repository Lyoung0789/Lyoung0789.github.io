---
layout: post
title:      "Rails Portfolio Project"
date:       2020-05-10 03:34:04 +0000
permalink:  rails_portfolio_project
---


Project 3! Okay here we go, for my third portfolio project I created a Handyman application in which users are able to book appointments with technicians that are signed up for the application. Users can also be managers and create Technicians and view their appointments. The relationships I have between my models are: 

-	User has_many Technicians, through appointments 
-	Technicians has_many_users through appointments 
-	Appointments belong_to both User and Technician. 

The first thing I did was to map out what my schema and relationships of my models would look like. When that was completed, I wrote out what functionality my users would have and how  they affect my technicians and vice versa. When all this was written out, it was time to start coding! Easy enough right? WRONG! 

After I created a brand spanking new rails project, I honestly had no idea where to start. I had so many notes that I couldn’t decide on how I should attack this project. So I took a step back and went step by step. I created the migration files and created the database first. Then in order, I started with the User(s) model and controller , the Session(s) controller, the Technician(s) model and controller and finally the Appointment(s) model and controller.  I decided the best way to work through this project was to “roughly” make everything work and address the bugs, validations, Omniauth, partials, helpers, and DRY methods for last. 

Working on this project, there were multiple times where I felt overwhelmed. But taking a step back,  and taking it step by step definitely helped the process. I learned so much during this project and I am eager to learn more! This has been my favorite project thus far!! Looking back at myself on day 1 I have learned so much!! I am so happy I decided to take this course and can’t wait to see what my future holds! More than halfway to the finish line! 

