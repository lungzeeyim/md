---
title: "Java Fundamental Part 1"
date: 2023-04-04T12:26:29+08:00
draft: true
---

Data Type
--------
--------
- Java data types:
    - basic data types
        - byte, short, int, long, float, double, char, boolean
    - reference data types
        - except bellowing
        - `String` and `Enum` are reference types
- calculation
    - `i++`, after this line and plus one
    - `++i`, plus one and then run the code
- `==` and `equals`
    - for `basic data types`, use `==` to determine if they are the **same value**
    - for `reference data types`
        - == to determine if they are same **object**, same **address**
        - `equals` to determine if they are **same value**, or customize the equal rules


`return` in `try-catch-finally`
-----------------
-----------------
```java
public static int test2() {
    int a = 1;
    try {
        System.out.println(a / 0);
        a = 2;
    } catch (ArithmeticException e) {
        a = 3;
        return a;
    } finally {
        a = 4; 
        return a; // a = 4 finally!!!
    }
}
```
In `try-catch-finally` statement, the `return` in `finally` must be ran.  

**Don't recommend to write this kind of confusing code.**


`try-with-resource`
-----------------
-----------------























