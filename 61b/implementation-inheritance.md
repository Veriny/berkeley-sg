---
description: Notes from Josh Hug's lecture videos.
---

# Implementation Inheritance

## Extends

`extends` is used when a class has an is-a relationship with another class. 

```java
public class Steven extends BaldMan {
    //Stuff...
}
```

In this example, `Steven` inherits from `BaldMan` the following.

* All instance and static variables.
* All methods.
* All nested classes.
* UNLESS they are private.
* ... and UNLESS the method is a constructor.

## super

In order to access members in the superclass, you must call the `super` keyword. This is useful for avoiding repetition, especially if you're overriding methods that use private fields and want to keep the original implementation.

```java
public class Steven extends BaldMan {
    @Override
    public void applyRogaine() {
        super.applyRogaine(); // Do everything the original method did...
        System.out.println("Steego"); // But also print this.
    }
}
```

{% hint style="warning" %}
The constructors of subclasses can call the constructor of the superclass using `super(params);`If you don't Java will do it implicitly.
{% endhint %}

## Encapsulation

Implementation inheritance breaks encapsulation in such a way that working changes to the superclass can cause issues in the subclass without any changes in the subclass.

