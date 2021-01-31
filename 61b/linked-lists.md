---
description: Notes from Josh Hug's lecture videos.
---

# Linked Lists in Java

A linked list is a  recursive object that contains a value and the next element in the list, which is another instance of itself.

```java
public class IntNode{
    private int item;
    private IntNode next;
    public IntNode(int item, IntList next){
        this.item = item;
        this.next = next;
    }
}
```

This is really bad, though, and it's a pain for users to use, so we can improve it.

## Improving the IntNode

In order to start fixing our `IntNode` let's build a new class that uses it, `SLList`. 

```java
public class SLList {
    private IntNode first;
    public SLList(int x) {
        first = new IntNode(x, null)
    }
}
```

{% hint style="warning" %}
Because we want to hide `IntNode` from anyone using the `SLList` class, we have made it `private`, making it inaccessible to the outside.
{% endhint %}

It's somewhat better, since there's no more need to, when creating a linked list, specify a null, e.g. `new IntNode(6, null)`.

Let's implement getters and setters for the first item in the list. We'll also nest the `IntNode` class inside of our `SLList`. Java supports nested classes!

```java
public class SLList {
    private IntNode first;
    /* We moved our IntNode class to the same file as this one.*/
    private static class IntNode{
        private int item;
        private IntList next;
        public IntList(int item, IntList next){
            this.item = item;
            this.next = next;
        }
    }
    public SLList(int x) {
        first = new IntNode(x, null)
    }
    /* Add a number to the front of the list*/
    public void addFirst(int x) {
        first = new IntNode(x, first);
    }
    
    /*Get the first item in the list.*/
    public int getFirst() {
        return first.item;
    }
}
```

{% hint style="warning" %}
Since there's no need for anything outside of `SLList` to manipulate an `IntNode`, we are free to make it `private`. Since it never uses anything outside of its own class, we can also make it `static`.
{% endhint %}

Now there's no more need for users, when constructing lists, to nest a bunch of `new IntNode()` calls, and they can just use the `addFirst` method if they want to extend the list.

| This is Better | This is Cringe |
| :--- | :--- |
| `SLList L = new SLList(3);` | `IntNode L = new IntNode(9, new IntNode(6, new IntNode(3, null)))` |
| `L.addFirst(6);` |  |
| `L.addFirst(9);` |  |

## Improving the SLList

Now that we've got our basic `SLList` structure down, we can improve it further by adding more methods for the user. 

```java
public class SLList {
    private IntNode first;
    /* Keep track of the size of the list so we don't have to compute it each
    time we want it*/
    private int size = 1;
    private static class IntNode{
        public int item;
        public IntList next;
        public IntList(int item, IntList next){
            this.item = item;
            this.next = next;
        }
    }
    public SLList(int x) {
        first = new IntNode(x, null);
    }
    public void addFirst(int x) {
        first = new IntNode(x, first);
        /*Increment the size of the list by one*/
        size += 1;
    }
    public int getFirst() {
        return first.item;
    }
    /* Adds an item to the end of the list, rather than the beginning.*/
    public void addLast(int x) {
        IntNode temp = first;
        while (temp.next != null) {
            temp = temp.next
        }
        temp.rest = new IntNode(x, null);
        /*Increment the size of the list by one*/
        size += 1;
    }
    /* Instead of recursively computing the size each time we want it, we
    just have a getter for the variable. */
    public int size() {
        return size;
    }
}
```

## The Empty List

Let's add another constructor so that we can account for having an empty `SLList`.

```java
public SLList() {
    first = null;
    size = 0;
}
```

This works fine for everything but ```addLast```, because in that method, we try to access the `.next` of `first`, which is not going to work because it is null. Let's see how we can fix that.

{% hint style="warning" %}
We can fix the above with a special case, but special cases are cringe. It's better for everything to work in one consistent way.
{% endhint %}

## Sentinel Node

Instead of using a special case, we can represent the empty list using a sentinel node, a special node that is always there.

```java
public class SLList {
    /* The first item of this list is at sentinel.next*/
    private IntNode sentinel;
    private int size = 1;
    private static class IntNode{
        public int item;
        public IntList next;
        public IntList(int item, IntList next){
            this.item = item;
            this.next = next;
        }
    }
    public SLList(int x) {
        sentinel = new IntNode(69, null);
        sentinel.next = new IntNode(x, null)
    }
    /*Our new constructor for an empty list — 69 is a dummy and will never
    be accessed.*/
    public SLList() {
        size = 0;
        sentinel = new IntNode(69, null);
    }
    public void addFirst(int x) {
        sentinel.next = new IntNode(x, sentinel.next);
        size += 1;
    }
    public int getFirst() {
        return sentinel.next.item;
    }
    public void addLast(int x) {
        /* Temp will never be null! Thus our problem is solved */
        IntNode temp = sentinel;
        while (temp.next != null) {
            temp = temp.next
        }
        temp.next = new IntNode(x, null);
        size += 1;
    }
    public int size() {
        return size;
    }
}
```

Because we rewrote our code in this way, we have the following **invariants** in mind!

* The first item in the linked list will always be at `sentinel.next`.
* In the `addLast` method, `temp` will never be null.

We don't have to write special cases for null anymore.

