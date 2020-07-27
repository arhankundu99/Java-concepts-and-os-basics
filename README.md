The main aim of oops is to implement real world entities.An object oriented language uses objects in programming
### Object
An object is an instance of class.An object consists of state(attributes), behaviour(methods) and identity.
### Class
A class is a blueprint from which you create an object.Class does not consume space.

### Polymorphism
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





