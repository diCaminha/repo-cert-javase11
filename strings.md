# Strings and StringBuilder

```java
String name = "Flurry";
```

We know that this is a reference type, but the interesting part is it not using the keyword *new*.

The String class is special and doesn't need the new keyword to be instanciated.

## Concatenation

take a look at the code below:
```java
int three = 3;
String four = "4";
System.out.println(1 + 2 + three + four);
```
the final answer is "64", due to the three rules:
1. If both operands are numeric, + means numeric addition.
2. If either operand is a String, + means concatenation.
3. The expression is evaluated left to right.



## Immutability

Once a String is created it is not allowed to change. It can't neither be larger or smaller.

a trick question, compile the code below:
```java
String s1 = "1";
String s2 = s1.concat("2");
s2.concat("3");
System.out.println(s2);
```
Did you say "12"? Good. The trick is to see if you forget that the String class is **immutable**
by throwing a method at you.


## The String Pool

Since Strings are everywhere in a program, so they will use a lot of memory. Java realizes that many Strings repeat in the program and solves this huge consumption of memory by creating a **string pool** which allows to reuse already created ones. In somewhere on the JVM there's a place for all the Strings created in the program.

*Note: there's a way where the String will not be loaded into the String Pool:*
```java
String name = "Fluffy"; //will to String pool
String name = new String("Fluffy"); //wiil NOT.
```


## Important String methods

1. length()

2. charAt()
```java
String string = "animals";
System.out.println(string.charAt(0)); // a
System.out.println(string.charAt(6)); // s
System.out.println(string.charAt(7)); // throws exception
```

3. indexOf()
```java
String string = "animals";
System.out.println(string.indexOf('a')); // 0
System.out.println(string.indexOf("al")); // 4
System.out.println(string.indexOf('a', 4)); // 4
System.out.println(string.indexOf("al", 5)); // -1
```

interesting point is that when searching indexOf for 'a' and 'al' it returns the same index.

4. substring()
```java
String string = "animals";
System.out.println(string.substring(3)); // mals
System.out.println(string.substring(string.indexOf('m'))); // mals
System.out.println(string.substring(3, 4)); // m
System.out.println(string.substring(3, 7)); // mals
```
5. equals() and equalsIgnoreCase()
   
   it returns true or false by comparing string values

```java
String name1 = "Denis";
String name2 = "DENIS";
System.out.println(name1.equals(name2)); //false
System.out.println(name1.equalsIgnoreCase(name2)); //true
```


## Using StringBuilder

A small program can create a lot of String objects very quickly.

StringBuilder class creates a String without storing all those interim String values. StringBuilder is not immutable.

```java
4: StringBuilder sb = new StringBuilder("start");
5: sb.append("+middle"); // sb = "start+middle"
6: StringBuilder same = sb.append("+end"); // "start+middle+end"
```
Line 5 adds text to the end of sb. It also returns a reference to sb, which is ignored. 

Line 6 also adds text to the end of sb and returns a reference to sb. This time the reference is
stored in same—which means sb and same point to the exact same object and would print
out the same value.

## StringBuilder vs StruingBuffer

When writing code that concatenates lots of strings, you better use StringBuilder.

StringBuffer does the same as StringBuilder, but slower since it is thread safe.


