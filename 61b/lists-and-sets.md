---
description: Adapted from Josh Hug's Lectures.
---

# Lists and Sets

## Sets

Sets are collections of items with no particular order. Duplicates are not allowed.

```java
Set<String> artifacts = new HashSet<>();
S.add("Gladiator's Finale");
S.add("Heart of Depths");
S.add("Blizzard Strayer");
S.add("Crimson Witch of Flames");
```

Here are some useful set methods.

| Method | What it does |
| :--- | :--- |
| `boolean add(Type thing)` | If the item is not already in the set, add it to the set. |
| `boolean contains(Object thing)` | Returns whether the set contains the thing or not. |
| ~~`int size()`~~ | Returns the number of items in the set. |
| `Object[] toArray()` | Returns an array containing all of the items in the set. |
| `void clear()` | Removes all of the elements from the set. |
| `boolean remove(Object thing)` | Removes the thing from the set if it is in it. |

## Disjoint Sets Data Structure

The disjoint set has two methods.

| Method | What it does |
| :--- | :--- |
| `void connect(Type x, Type y)` | Connects x and y. |
| `boolean isConnected(Type x, Type y)` | Returns whether x and y are connected. |

Instead of keeping track of each individual connection, we can just keep track of the sets that each item belongs to.  


| Operation | Resultant Set\(s\) |
| :--- | :--- |
| `connect(1, 3)` | `{1, 3}, {2}` |
| `connect(3, 2)` | `{1, 2, 3}` |

### Quick Find

In Quick Find, we represent a disjoint set as a list of integers, where the ith entry gives the set number of i. Therefore, `connect(p, q)` changes entries that are equal to `id[p]` to `id[q]`. Connect is $$\Theta(N)$$ , but checking if two items are connected is constant time!

### Quick Union

Similar to Quick Find, but instead of a set id, the value we store in the array is the index of the item's parent. To connect two items, we find the roots of the two items we want to connect, and connect them.

The problem is, as the set gets larger, finding the root of any item might start taking a while. This means that for both `connect` and `isConnected`, our worst case runtimes are $$O(N)$$ .

### Weighted Quick Union

Weighted quick union avoids tall trees \(and therefore an expensive `root`\) by always linking the root of the **smaller** tree to the **larger** tree. Size is based on **number of elements** in the tree. In this case, worst case tree height is $$\Theta(\log N)$$ . Therefore, connecting and checking connections have logarithmic time performance.

### Weighted Quick Union + Path Compression

Like weighted quick union, but when we check connections, we tie all nodes seen on the way down the tree to the root. This flattens the tree over and over, improving our $$\log$$ runtime to $$lg*$$, which is so efficient it might as well be constant \(amortized - "average" constant time\).

## Lists in Java

Lists are a useful interface in hava. They are instantiated as follows.

```java
List<Steven> lst = new List<>();
```

The two most common ones in 61B are `ArrayList` and `LinkedList`. An example of instantiating an `ArrayList` and performing some operations on it are shown below.

```java
ArrayList<Integer> lst = new ArrayList<>(); 
//The type of object that the list holds goes in the <>. Primitives not allowed.
lst.add(6);
lst.add(4);
lst.add(69);
lst.contains(42); //Returns false
lst.size(); //3
```

Here is a partial list of list methods.



