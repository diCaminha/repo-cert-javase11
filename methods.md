# Methods

Define and use fields and methods, including instance, static and overloaded methods

## Varargs

- must be the last element in a method's parameter list.
- you can only have 1 vararg per method
  
```java
 public static void walk(int start, int... nums) {
    System.out.println(nums.length);
}

public static void main(String[] args) {
    walk(1); // 0
    walk(1, 2); // 1
}
```

## Applying access modifiers

### Private

only code in the same class can call **private method** or access **private fields**

### Default

Also known as Private package, it can only be called by others in the same package.

It's the deefault access modifiers of methods if it is not explicit informed by the code.


### Protected

Allows everything that Default does, but more! It also lets the children (extended classes) to access and call methods.

```java
public class Bird {
    protected void floatInWater() {}
}

public class Gosling extends Bird {
    public void swim() {
        floatInWater();
    }
}
```

## Public

It's open for all classes from everywhere.

## Designing Static Methods and Fields

So far, we've being looking at instance methods. But exists static methods, the ones that does not require a instance of the class to be called.

- It's shared among all users of the class.

- static vs instance:
    A static member CANNOT call an instance member.

    common mistake:
    ```java
        public class Static {
            private String name = "Static class";
            public static void first() { }
            public static void second() { }
            public void third() { System.out.println(name); }
            public static void main(String args[]) {
                first();
                second();
                third(); // DOES NOT COMPILE
        } }
    ```

## Overloading Methods


