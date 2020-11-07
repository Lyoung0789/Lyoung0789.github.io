---
layout: post
title:      "Four Pillars of Object Oriented Programming"
date:       2020-11-07 17:21:00 +0000
permalink:  four_pillars_of_object_oriented_programming
---

If you have been following my recent blog posts I have mostly been reviewing concepts in React and JavaScript. This past week I have been diving into Object Oriented Programming (OOP). In this blog post I will go over the four pillars of Object Oriented Programming. Before we start, there are many Object Oriented Programming languages, but some sample code and concepts that may be provided will be in terms of Java. 

## What is Object Oriented Programming?
So before we start listing off the “Four Pillars” we need to talk about what Object Oriented Programming is. Object Oriented Programming is a coding paradigm that relies on the concept of classes and objects. Objects can be defined as instances of classes, and classes can essentially be defined as the “blueprint” used to create objects. All of OOP is supported by 4 major concepts, Inheritance, Polymorphism, Encapsulation, Abstraction. 

## Inheritance
In Java, Inheritance is a mechanism in which one object acquires all the properties and behaviors of a parent object. This means that we are able to create new classes that are built upon existing classes. When we create new classes from existing classes the new class is able to use all the methods and fields of the existing class. The new class is often referred to as the Child or Sub Class and the existing class is referred to as the Super or Parent Class. When inheriting from the Parent class, the Child class uses the `extends` keyword. This parent-child relationship is also known as a “IS-A” relationship.

```
Example: 
class Person {
 String name= “Anthony”;
}

class Student extends Person {
float gpa = 3.9;


Public static void main(String args []){
Student s = new Student; 
System.out.println(“My name is:” + s.name);
System.out.println(“My gpa is:” + s.gpa);
}
}
```

Output: 
My name is: Anthony
My gpa is: 3.9

As you can see in the example above we have a Parent class called Person, and a Child Class, Student that “extends” the Person class. This allows any new instances of Student to use the “name” variable that was defined in the Person class. (Student IS-A Person).

There are three types of Inheritance in Java:
1. Single Inheritance: This is when a Child Class extends a Parent Class.
2. Multilevel Inheritance: Multiple layer of Parent and Child classes. This is where you can use the terms Grandchild or Grandparent.  A Child class extends a Parent Class, that Parent Class extends a higher Parent or Grandparent class. 
3. Hierarchical Inheritance: more than one Child Class can have the same Parent Class. 

## Polymorphism
The second pillar we are going to discuss is Polymorphism. The definition of Polymorphism is the ability of an object to take on many forms. In Java,  every object that can pass more than one IS-A test is polymorphic. If we take the example from the Inheritance section, a Student IS-A Person, a Student IS-A Student and a Student IS-A Object. Which means that every Java object is Polymorphic. 

### Overloading vs. Overridding
Overloading and Overriding are big concepts in the Four Pillars. Overloading will allow different methods but with the same name, but with different number of parameters or different type of parameters or both. Let me show you an example

```
class Adder {
static int add(int a, int b){return a+b;}
static int add(int a, int b, int c){return a+b+c;}
}

class Test{
public static void main(String args []){
System.out.println(Adder.add(1,1));
System.out.println(Adder.add(1,1,1));
}
}
```

In the above example the output will be 2 and 3. As you can see there are two methods with the same name but different number of parameters. Depending on the number of parameters the method with the matching amount of parameters will be executed. 

```
class Adder {
static int add(int a, int b){return a+b;}
static double add(double a, double b){return a+b+c;}
}

class Test{
public static void main(String args []){
System.out.println(Adder.add(1,1));
System.out.println(Adder.add(1.1,1.1));
}
}
```

In the above example the output will be 2 and 2.2. As you can see the type of parameters are different. So overloading will occur. 

Overriding is when the Child Class has the same method as declared in the Parent Class. There are three rules for Overriding. 
1. The method must have the same name as the Parent Class. 
2. The method must have the same parameter as the Parent Class. 
3. There has to be an IS-A relationship.

```
class Person {
public void display(){
System.out.println(“this is from the parent class”);
}
}

class Student extends Person {
Public void display(){
System.out.println(“this is from the child class”);
}

Public static void main(String args []){
Person p = new Person; 
p.display();
Person s = new Student;
s.display();
}
```

Output: 
“this is from the parent class 
“this if from the child class”

As you can see in the above example we have a Parent class and Child class with the same method name but with different behaviors. Even though s is an Animal reference but a Student Object “s.display()” will display what the method in the Student class has defined. 

One thing to note is that the methods in both of these classes are public, if they were static or final Overriding is not possible. 

## Encapsulation
Encapsulation is the process of wrapping code and data together into a single unit. This means that data or variables of a class will be hidden from other classes and can only be accessed through their own methods. Encapsulation is also known as data hiding. This allows the control over the data, data hiding, and makes testing so much easier. 

### Readers and Writers
As I mentioned the data can only be accessed through their own methods. This is where readers and writers come to play. These methods must be defined in the class itself. The Reader-only methods will allow other classes to only access the data for reading purposes only. And the Writer-only method allows other classes to change the data but not read.

## Abstraction
Abstraction is the process of hiding the implementation details and showing only functionality to the user. In simpler words it shows what an object does, but not how it does it. This is done by Abstract classes and methods. 

## Conclusion
The Four Pillars of Object Orientation Project are Inheritance, Polymorphism, Encapsulation, and Abstraction. This is fundamentally important when learning any OOP language. And will definitely be in interviews. So read up on it and learn more! That’s all for now! Happy Hacking!!


