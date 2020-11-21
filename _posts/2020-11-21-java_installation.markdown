---
layout: post
title:      "Java Installation"
date:       2020-11-21 16:37:08 +0000
permalink:  java_installation
---


Hello all and welcome back! In my recent blog posts I have been covering concepts mainly based in JavaScript and Ruby. But today we are going to start to switch gears and start the process of coding in another OOP language. Java! 

In this blog post I am going to be going over how to set up your environment and provide some links to some of my favorite Java IDE’s.From my last blog post I switched over to a Windows OS, so no more Mac for now. Let’s jump into it!

## JDK
The first thing you should do is check if you already have java installed on your computer. In your windows command prompt type `java -version` and hit enter. If you get results with a java version you already have it installed! Good for you! If not keep following this blog. 

If you do not have Java installed on your pc you need to download the JDK. JDK stands for Java Development Kit. If you plan on coding in Java, you will most likely also hear terms like JDM, JRE, and javac. I won’t go into detail on these for now but know that installing the JDK will provide your environment with all these tools and more. 

To install the latest version of JDK head over to: 

[Java Development Kit](https://www.oracle.com/java/technologies/javase-downloads.html)

Click on  “JDK Download”, you'll be redirected to another page. From here select your operating System and download the latest version. When you have downloaded the JDK open it up and start the installation process. After you go through the process of installation go back to your command prompt and type in `java -version` one more time. If you installed it correctly you should be able to see the latest version of java. Something like this: 

```
java version "15.0.1" 2020-10-20
Java(TM) SE Runtime Environment (build 15.0.1+9-18)
Java HotSpot(TM) 64-Bit Server VM (build 15.0.1+9-18, mixed mode, s
```

If you see this you are all set to start coding in Java! 

## Testing
Okay so we have the JDK installed. So let’s test this bad boy out with the classic “Hello World!” application. 

Let’s open up Notepad and create a class called “HelloWorld” with a main method that prints out “Hello World!” to the screen. Since you may be new to Java there are certain syntax rules we 

need to follow before being able to properly run a program in Java. I won’t go over those rules right now, so I have provided the code for the application. 

``` 
public class HelloWorld {

	public static void main(String[] args){
		System.out.println("Hello World!")
	}


}
```

Save this file with a “.java” file type. Be sure to change the file type to “.java”. In the command prompt, navigate to the directory of the file. Then type in `javac HelloWorld.java`. This will compile the code and create a “HelloWorld.class” file in the same directory. Now we have the compiled code, we can execute the new “HelloWorld.class” file by typing in `java HelloWorld`. 

Now you should see the output `Hello World!` to the screen!  

## IDE
I displayed how we can write code in a notepad and run it just as if we were in an IDE. But coding in Notepad can get really confusing for longer and more complicated applications. This is where IDE’s come along. You should have some experience with IDE’s, like Visual Studios or Atom. For Java programming my favorite IDE is IntelliJ. This can be found and installed [here]( https://www.jetbrains.com/idea/). 

Another IDE that is very popular is Eclipse that can be found [here](https://www.eclipse.org/ide/). 

These are both very popular IDE’s and honestly it’s personal preference to which you like more. 


Well that’s it! You are ready to start coding in Java. I hope this was helpful, happy hacking!

