---
layout: post
title:      "Access Modifiers"
date:       2020-11-28 17:48:56 +0000
permalink:  access_modifiers
---


If you have been following my past blog posts, you may have noticed I have been going over some basic concepts of Java programming. And this post is no different! Today I will be going over Access Modifiers in Java. Let’s get started!

Before we get started I would like to define what exactly an Access Modifier is. In Java an Access Modifier restricts the access of a class, constructor, data member and methods in another class. There are 4 types of Access Modifiers.

1. Default
2. Private
3. Protected 
4. Public

To use these Access Modifiers you would use them as a keyword in front of what you are restricting. The only Access Modifier that does not use a keyword is Default. Lets go over Default first. 

Also, I will be using the word “package” quite frequently. Just know a “package” is used in Java to pretty much group together related classes. It's kind of like a folder holding similar files. There is so much more to packages, but I wont get into that today. For this blog post just use the “file directory” analogy and you should be good. 

## Default
When we don't specify an Access Modifier Java automatically makes whatever we are creating Default. 

The Default Access Modifier is probably the simplest and easiest to understand out of the four. Default signifies that it restricts access from outside of the package that it is in. Pretty much it only can be accessed by whatever is in the package where it is created. It can be accessed by other classes as long as they are both in the same package. 


## Private
The next Access Modifier I will go over is Private. To restrict to Private, use the “private” keyword.

The Private Access Modifier is another easy modifier to understand. If you apply the private keyword it restricts access to only within the class that it is defined. This means no sub classes, no other classes within the package, or no classes in other packages can access it. 

## Protected
The Protected modifier can be used, by using the “protected” keyword. 

This modifier allows access within the class, and within the package. Just like the Default Access Modifier. But it also adds another level of access to child-classes outside of the package. If you haven’t read my older post on The Four Pillars of OOP, Inheritance creates parent and child classes. A child-class inherits from a parent class. So having a Protected Access Modifier means that the data can be accessed within the class and within the package, but also outside of the package, as long as the class accessing it, is a child-class. 

This Access Modifier can be a little confusing at first but after practicing with it, you'll get the hang of it. 

## Public
The final Access Modifier is Public. To restrict information to Public, by using the “public” keyword. 

So I lied earlier, the easiest Access Modifier to understand is the Public modifier. Having the “public” keyword allows access from everywhere. There are no restrictions implemented when using this Access Modifier. It can be accessed from within and outside the package. When being accessed outside the package it does not have to be a child-class, like the Protected Access Modifier. 

## Conclusion
That's it! Those are the four Access Modifiers in Java. I found it easy to understand when reading it. But when I put it into practice, that's where I would get confused. Make sure you practice over and over. 

In Java there are also modifiers called Non-Access Modifiers. I won't go over those in this post, but maybe in future ones. Till then, Happy Hacking!


