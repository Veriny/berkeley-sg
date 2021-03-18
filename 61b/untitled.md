---
description: Notes from Josh Hug's lecture videos.
---

# Comparables and Iterators

## Iterators

Iterators are useful for data structures that store objects, as they allow users to go through them one by one. Syntax wise, if `Steven` is a data structure, then we must do the following.

1. `Steven<T>` implements `Iterable<T>`. It implements its interface method, `iterator();`, that returns a `StevenIterator`.
2. The `Steven` class should have a `StevenIterator` subclass, that implements `Iterable<T>`.
3. `StevenIterable` should implement `Iterable`'s interface methods, `T next();` and `boolean hasNext();`.
4. `StevenInstance.iterator();` should return `new StevenIterator();`.

{% hint style="warning" %}
Many Java built-in data structures, such as `ArrayList` and `LinkedList`, already implement `Iterable<T>`, which is useful because you can get an `Iterator` object from them whenever you want.
{% endhint %}

If an object implements `Iterable`, you can use an enhanced for loop on it.

```java
for (int i : lst) {
    System.out.println(i);
}
```

## Comparables

A lot of data structures, such as BSTs, rely on objects being comparable. We can make any object we want comparable by doing the following.

1. The object should implement `Comparable`.
2. The object should then implement its interface method,  `int compareTo(T item);`. This method usually returns negative if the object invoking it is less than item, positive if vice versa, and zero if equal.



