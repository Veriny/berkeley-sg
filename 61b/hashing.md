---
description: Adapted from Josh Hug's lectures
---

# Hashing

The strength of arrays comes from the fact that accessing an element in an array takes **constant time**. One way we can do this is by indexing by data.

## Indexing by Data

One way we can exploit the constant runtime of accessing an element in an array is to use the data as the index. For example,

```text
boolean[] steven = new boolean[100000]
```

we could use the above code to store any number in our "set" between 0 and 99999. Just `steven[0] = true` and boom, we have 0 in our set. If we want to take it out, set it to false. 

How is this accomplished with non-integer data types?

In the case of English words, we can just represent each word as a number and just do what we did before. For example, we can represent each letter of a word as its index in the alphabet \(for example, c is the third letter so we represent it with 3\) each multiplied by a power of 27 and added with the other letters in the word to avoid any two words taking up the same spot. As long as we pick a base that is creater than or equal to 26, \(we chose 27\) we will get a unique number for each string.

However, we can't store things like numbers and symbols. To fix this, we will use the ASCII number set to represent each possible printable character. We would use base 126 to guarantee that all possible strings have a unique number.

![Source: Ohio State University](../.gitbook/assets/image%20%288%29.png)

However, if we tried to use unicode and support other languages, we would end up with numbers so large that we would be faced with integer overflow. This means that strings will no longer have unique representations. Taking overflow into account, two strings can now have the same value!

## Hash Codes and Hash Tables

The name of the number we computed in the previous section is known as a hash code. The pigeonhole principle states that collisions are inevitable.

In order to deal with collisions, we will use hash tables. The basic idea of this is that, unlike before, when we used an array of booleans, we will use an array of "buckets" which will store any number of items that contain the same hashcode.

If our bucket is a linked list, than in the worst case, our runtime will be $$\text{O}(Q)$$ where Q is the length of the longest bucket. We also have the issue that we have billions of buckets, which is a massive waste of memory.

We can solve both these problems by implementing resizing — have a small number of buckets, and if it gets too full, add more buckets. Resizing will take $$\Theta(N)$$ time, because we have to redistribute every single item.

{% hint style="info" %}
We can decide when to resize based on a **load factor** $$\frac{M}{N}$$ , where $$M$$ is the number of buckets and $$N$$ is the number of items in the hashmap.
{% endhint %}

Hash codes themselves MUST:

* Be deterministic — repeated calls on the same object must return the same code.
* Be consistent with `.equals` — if two objects are equal, then they must return the same code.





