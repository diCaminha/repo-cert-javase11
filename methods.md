# Methods

Define and use fields and methods, including instance, static and overloaded methods

## Varargs

- must be the last element in a method's parameter list.
- you can only have 1 vararg per method
  
```java
public void walk1(int... nums) {}
public void walk3(int... nums, int start) { } //DOES NOT COMPILE
```
