---
description: Notes from Josh Hug's lecture videos.
---

# Linked Lists

A linked list is a simple recursive object that at the most basic level contains a value and the next element in the list,

```java
public class IntNode{
    private int item;
    private IntList next;
    public IntList(int item, IntList next){
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

