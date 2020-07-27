The main aim of oops is to implement real world entities.An object oriented language uses objects in programming
## Object
An object is an instance of class.An object consists of state(attributes), behaviour(methods) and identity.
## Class
A class is a blueprint from which you create an object.Class does not consume space.

## Polymorphism
It refers to differentiating between methods of same name that differ on number of parameters or type of parameters.
```java
public int sum(int a, int b){return a+b;}
public int sum(int a, int b, int c){return a+b+c;}
public double sum(double a, double b){return a+b;}
```
Types of polymorphism:
1) Overloading.
2) Overriding.(If we inherit the methods of a parent class using `extends` keyword and we want to modify a inherited method in the child class. This modification of inherited method is known as overriding).We can only override methods, not class variables
Java provides operator overloading also. `+` can be used for addition of 2 numbers and concatenation of 2 strings. 

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

## Abstraction (Implementation hiding)
Abstraction can be achieved through abstract classes(0-100%) or interfaces(100 %).An abstract method has no body.

Why use abstraction?
To hide implementation details. (Real life Eg: a man is driving a car. He knows that by pressing break, the car will slow down. but he does not know how the car slows down.This is an example of abstraction.

## Static and final in java
Static methods and variables are a property of class. They can be called without creating an object. Same static variable is shared between all instances of class. Final variables cannot be changed after assignment.

## Access modifiers in java

