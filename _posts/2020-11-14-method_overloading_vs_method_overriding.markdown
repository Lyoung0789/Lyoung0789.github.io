---
layout: post
title:      "Method Overloading vs. Method Overriding"
date:       2020-11-14 19:04:11 +0000
permalink:  method_overloading_vs_method_overriding
---


Hi Guys, welcome back! In my last blog post we discussed the 4 pillars of Object Oriented Programming. Inheritance, Polymorphism, Abstraction and Encapsulation. In this blog post I am going to be reviewing another major concept in Java programming called Overloading and Overriding. 

Before I get into it I want to discuss the basic differences of Compile time and Run time polymorphism. For just a review Polymorphism is one of the 4 pillars of Object Oriented Programing. The literal meaning means to have “Many Forms”. Simply it means for an object to be able to have many forms of other objects. There are two types of polymorphism, compile time and run time, which is very important for the concept of Overloading and Overriding. 

Compile Time is the stage of programming where the code that you write is converted into executable code or “compiled”.
Run Time is the stage of programming when the code that is compiled gets executed. 

Now these two stages go way more in depth, but this is roughly the difference between the two. Since these are two different stages, they produce different exceptions which will not be discussed in this blog post but maybe in a later one?

So we know what Compile time and Run time are, what does this have to do with Overloading and Overriding?

## Method Overloading

Overloading usually occurs in one class but can also occur in a parent child class relationship,  an example of Compile Time Polymorphism. This occurs when we have more than one method in the same class, with the same name but with different parameters. There are three ways to Overload a method

The number of parameters are different. For example: 
```
void print(String name, int age){
   System.out.println(name + " is " + age + " years old.");
}

void print (String name, String species, int age ){
   System.out.println(name + " the " + species + " is " + age + " years old.");
}

The data type of parameters are different: 
void print(String name, int age){
   System.out.println(name + " is " + age + " years old.");
}
void print (int age, int numberOfSiblings ){
   System.out.println("Hello I am " + age + " years old and have " + numberOfSiblings + " siblings");
}

The order of parameters are different: 
void print(String name, int age){
   System.out.println(name + " is " + age + " years old.");
}

void print(int age, String name){
   System.out.println("Hello this is different. I am  " + age + " years old and my name is " + name);
}
```

One common example of Method Overloading is Overloading Constructors. In Java when we create a class Java automatically creates a default Constructor. We can Overload this constructor by creating our own. 

## Method Overriding

Method Overriding occurs in a parent-child relationship and is an example of Run Time Polymorphism. Method Overriding allows the child class to provide a unique or specific implementation of a method that is inherited from a parent class. For example: 

```
class Animal {
   void print(){
       System.out.println("Hi I am an Animal");
   }
}

class Monkey extends Animal {
   void print(){
       System.out.println("Hi I am a Monkey");
   }
}

public class Main {

   public static void main(String[] args) {
     Monkey george = new Monkey();
     george.print();
		      Animal creature = new Animal();
     creature.print();
   }
}
```

In the above example we have an Animal parent class and a Monkey child class that extends or inherits from Animal. In both classes we have two methods with the same name and parameters but different implementations. When we create objects of both classes and call the .print() we get two unique print statements. 

There are a couple rules to Overriding Methods: 
Methods with the access modifier “private” cannot be overridden. 
Methods with the “final” keyword cannot be overridden. 
Methods with the “static” keyword cannot be overridden. 
The overriding method must have the same return type. 

## Conclusion
The two main differences on Method Overloading and Method Overriding occurs in their parameters: 

Overloading occurs when we have the same method name but different parameters, can occur in the same class or in a parent-child relationship. An example of Compile Time Polymorphism. 

Overriding occurs when we have the same method name and same parameters in a parent-child relationship. An example of Run Time Polymorphism. 

I hope this blog post was helpful. Until next time Happy Hacking!



