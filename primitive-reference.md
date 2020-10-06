# Primitive vs Reference Types

## Primitives
These eight data types represent the building blocks for Java objects, because all Java objects are just a complex collection of these primitive data types

- boolean | true or false
- byte | 8 bits
- short | 16 bits
- int | 32 bits
- long | 64 bits
- double | 64 bits
- float | 32 bits
- char | 16 bits


*Note: you can have underscore ( _ ) in the middle of the value numbers. ex:* 

` int million = 1_000_000 //it compiles`

`int million = 1.000_000 //it does not compile`

*Note: to set the value for a long primitive value, you should add a L in the end of the value:*

`long numberLong = 11111110000000 //it does not compile`

`long numberLong = 11111110000000L /it works!`


## Reference

 refers to an object (an instance of a class).

references do not hold the value
of the object they refer to. Instead, a reference “points” to an object by storing the memory
address where the object is located, a concept referred to as a pointer. 


## Differences:
- primitives cannot have **null** values
- primitives do not have methods declared on them
- primitives has lowecase names by convention
