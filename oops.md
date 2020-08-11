The main aim of oops is to implement real world entities.An object oriented language uses objects in programming
## Object
An object is an instance of class.An object consists of state(attributes), behaviour(methods) and identity.
## Class
A class is a blueprint from which you create an object.Class does not consume space.
## Constructor
A constructor is a block of code which initialises the object. It is not a method since it does not have a return type. 

## Polymorphism
It refers to differentiating between methods of same name that differ on number of parameters or type of parameters.
```java
public int sum(int a, int b){return a+b;}
public int sum(int a, int b, int c){return a+b+c;}
public double sum(double a, double b){return a+b;}
```
Types of polymorphism:
1) Overloading. (calls to its methods are done at static binding)
2) Overriding.(If we inherit the methods of a parent class using `extends` keyword and we want to modify a inherited method in the child class. This modification of inherited method is known as overriding).(calls to its methods are done at dynamic binding).We can only override methods, not class variables
Java provides operator overloading also. `+` can be used for addition of 2 numbers and concatenation of 2 strings. 

NOTE: Late binding is only used to public access members of a class.
NOTE: STATIC and FINAL Methods CANNOT be overriden.Final methods can be inherited. Static methods CANNOT be inherited.
```java
class A {
    public static void display() {
        System.out.println("Inside static method of superclass");
    }
}

class B extends A {
    public void show() {
        display();
    }

    public static void display() {
        System.out.println("Inside static method of this class");
    }
}

public class Test {
    public static void main(String[] args) {
        B b = new B();
        // prints: Inside static method of this class
        b.display();

        A a = new B();
        // prints: Inside static method of superclass
        a.display();
    }
}
```
## Inheritance
Inheriting the methods of parent class using `extends` keyword.

Types of inheritance:
1) Single inheritance.(A is the parent class and B is the child class)
2) Multilevel inheritance.(A is the base class, B inherits from A, C inherits from B)
3) Hierarchical inheritance.(A is the base class. B inherits from A, C inherits from A)
4) Multiple inheritance: (A and B are base class. C inherits from A and B)
   PLEASE NOTE that java DOES NOT support multiple inheritance using classes.We can achieve multiple inheritance in java using interfaces. Interface Eg: Comparator interface in java.
   ```java
   interface A{
        void methodA();
   }
   interface B{
        void methodB();
   }
   interface C extends A, B{
        void methodC();
   }
   class child implements C{
        void methodA(){
            print("methodA");
        }
        void methodB(){
            print("methodB");
        }
        void methodC(){
            print("methodC");
        }
    }
    ```
    Note that the interfaces have abstract methods (There is no body to the methods).In interfaces all the methods are public and abstract.All the fields are public, static and final.
    
## Encapsulation (Data Hiding)
Encapsulation is like a shield to data. Outside this shield we cannot access this data.
In encapsulation, we make the fields private and write public methods to change and access them.

What is the benefit of encapsulation?
It hides the data preventing unauthorized access to them.
We can make the variables of the class as read-only or write-only depending on our requirement.

## Abstraction (Implementation hiding)
Abstraction: Showing Functionality and hiding implementation details.
Abstraction can be achieved through abstract classes(0-100%) or interfaces(100 %).An abstract method has no body.
NOTE: We cannot create an object of abstract class. 

Why use abstraction?
** Abstraction helps to reduce the complexity of the design and implementation process of software. **
To hide implementation details. (Real life Eg: a man is driving a car. He knows that by pressing break, the car will slow down. but he does not know how the car slows down.This is an example of abstraction.
To achieve security - hide certain details and only show the important details of an object.
Abstract methods are mostly declared where two or more subclasses are also doing the same thing in different ways through different implementations.

## Static and final in java
Static methods and variables are a property of class. They can be called without creating an object. Same static variable is shared between all instances of class. Final variables cannot be changed after assignment.
1) Static methods can be inherited but cannot be overriden.
2) Final methods can be inherited and but not overriden. 
3) We can overload a static method and convert it into non-startic method (As long as parameters are different)
4) A static method can call only other static methods; it cannot call a non-static method.(Non static methods can access static data members and static methods)
5) static methods can ONLY access static methods and static data member.
6) Final Class cannot be inherited

```java
public class Writer {
    public static void write() {
        System.out.println("Writing");
    }
}

public class Author extends Writer {
    public static void write() {
        System.out.println("Writing book");
    }
}

public class Programmer extends Writer {

    public static void write() {
        System.out.println("Writing code");
    }

    public static void main(String[] args) {
        Writer w = new Programmer();
        w.write();

        Writer secondWriter = new Author();
        secondWriter.write();

        Writer thirdWriter = null;
        thirdWriter.write();

        Author firstAuthor = new Author();
        firstAuthor.write();
    }
}
```

Output:
```java
Writing
Writing
Writing
Writing book
```

## Access modifiers in java
There are 4 types of access modifiers in java
1) Default (No keyword required)
2) Private
3) Public
4) Protected

Private: Private methods or variables can be ONLY accessed within class only.Even if we inherit this class, we cannot access the private methods from child class.

Public: Public methods or classes or fields can be accessed from anywhere.

Default: Default methods can be accessed within the package only.

Protected: Protected methods can be accessed with the package and different package subclass.

![alt text](https://github.com/arhankundu99/Java-oops/blob/master/Access-Modifiers-in-Java.png)

## Super keyword
Super keyword is used to refer to parent class objects from child class.
```java
class A
{   
    A(){
        System.out.println("This is constructor A");
    }
    void method() 
    { 
        System.out.println("This is class A"); 
    } 
} 
class B extends A
{ 
    B(){
        super() // calls the construtor of class A
        System.out.println("This is constructor B");
    }
    void method() 
    { 
        super.method() // calls method function of A
        System.out.println("This is class B"); 
    } 
} 
```
NOTE: Call to super() must be first statement in Derived Class constructor.

## this keyword
`this` keyword is used to refer to the current instance of the class. `this` keyword is used to access the variables of the class. `this` keyword is similar to python's `self` keyword. `__init__` function in python is the constructor of the class.
