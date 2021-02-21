---
description: Notes from Josh Hug's lecture videos.
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

{% hint style="success" %}
TODO: Fill in information about lists.
{% endhint %}

