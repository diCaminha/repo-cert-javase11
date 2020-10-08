# Objects

All classes inherit from the same object: 

**java.lang.Object**

The compiler automatically insert code into any class that does not inherit other class.

## Order of initialization

The constructor runs after all fields and instance initializer blocks have run.

```java
public class Chick {
private String name = "Fluffy";
{ System.out.println("setting field"); }
public Chick() {
name = "Tiny";
System.out.println("setting constructor");
}
public static void main(String[] args) {
Chick chick = new Chick();
System.out.println(chick.name); } }
```

Running the code above will result in order:

setting field

setting constructor

Tiny

So first it will run the print statement in instance initializer in line 10, and then once all instance initializer have run, it will run the constructor

*Note: you CANNOT refer to a variable before it has been initialized:*

```java
{ System.out.println(name); } // DOES NOT COMPILE
private String name = "Fluffy";

```

# super() and this()

They should be the first statement under the constructor.

```java
public class Zoo {
 public Zoo() {
 System.out.println("Zoo created");
 super(); // DOES NOT COMPILE
 }
}
```

Note: Java compiler automatically adds a super() call under the constructor in child that did not explicity calls the parent super();


Take a look at this example:

```java
public class Mammal {
 public Mammal(int age) {
 }
}
public class Elephant extends Mammal { // DOES NOT COMPILE
}
```

the Mamal class only has one constructor and does not have a no-argument constructor by default nor explicity. So, the Elephant inherit the Mamal and MUST explicity calls the method from its super with parameters.



## Destructing the Object: GC

An object remains on the heap until it is no longer reachable. An object is no longer reacheble when one of two situations occurs:

 ■ The object no longer has any references pointing to it.
 
 ■ All references to the object have gone out of scope.