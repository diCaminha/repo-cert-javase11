# Local Variable Type Inference

Since JDK 10, we can use the type *var* as a type for a variable. So Java will do the hard work to identify the type for that variable.

So: Enhance the java language to extend type inference to declaration of local variables with initializers.

*Note: it works only for local variables*
```java
var list = new ArrayList<String>();
var stream = list.stream();
```

for both assignments above, the jvm will infer types for list and stream.

A great good example is when using loops:

```java
for (var x = 0; x < 3; x++) 
    System.out.println(arr[x] + "\n"); 
```


## Not allowed when:

1. In class field
```java
class A { 
    var x; /* Error: class variables can't be declared 
            using 'var'. Datatype needs 
             to be explicitly mentioned*/
} 
```

2. Uninitialized local variables

If a local variables is declared as var but not initialized (referenced to a value) it will give compiler error:

`var x;  \\ERROR`

3. Parameter for a method

` void show(var a) {} //ERROR`

4. Return type of method

`var aMethod() //ERROR`

5. Can't be initialized as null


