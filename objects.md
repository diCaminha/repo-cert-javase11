# Objects

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
