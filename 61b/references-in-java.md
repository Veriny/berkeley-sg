---
description: Notes from Josh Hug's lecture videos.
---

# References in Java

## Bits — How Computers Store Information

Computers store information in **bits**, which is just a bunch of zeroes and ones. 

In Java, when you **declare** a variable, like as follows —

```java
int x;
double steven;
```

The computer sets aside a box exactly enough bits large to hold a thing of that type. For example, an int is 32 bits and a double is 64 bits. 

When you **assign** a value to a variable, Java assigns the corresponding box of memory with the bits that correspond to the value you assign.

This is the case for **primitive types.**

{% hint style="success" %}
The **Golden Rule of Equals** states that when you set two variables equal to each other, all of the bits of one variable \(RHS\) get copied to the other \(LHS\).
{% endhint %}

## Reference Types and Object Instantiations

When an object is instantiated, i.e. through the `new` keyword, Java allocates a box of bits for each instance variable and fills them with some default value, after which the constructor fills them with some other value.

Java then finds however many bits the size of the object is in memory, and fill in those bits with the information of the object.

**The** `new` **keyword then returns the nth bit at which the object is located, which is stored in the variable. When a reference type is instantiated, it is always given a box of 64 bits.** 

```java
Steven a;
a = new Steven("bald");
Steven b;
b = a;
```

In the above example, `b` and `a` refer to the same object, following with the Golden Rule of Equals — the location of the bald Steven in memory is copied into `b`.

## Pass-By-Value

**Pass-by-value** follows the same rules as before — bits are always just copied into new scopes on method calls. 

For example,

```java
Steven a = new Steven("not bald");

public static void ageTenYears(Steven s) {
    s.hairStatus = "bald";
}

ageTenYears(a);
```

would turn the original steven bald, since all of the bits of `a` were copied into `s`

