# PriorityQueue and Heap

## Priority Queues

A minPQ is a collection of items where the smallest item is kept track of. You can add items to it, get the smallest item from it, and remove the smallest item from it. Priority queues in general can use a different comparison \(a minPQ compares by size, holding the minimum at any point in time.\)

## Heaps

A binary min-heap is a binary tree where every node is less than or equal to both of its children. A tree is complete if it's missing items only at the bottom level and all nodes are as far left as possible.

### Insertion:

* Add to end of heap.
* Swap with parents until we have a heap again.

### Deletion:

* Swap the last item of the heap into the root.
* Sink down the hierarchy.

### Representation

Because a heap is a complete tree, we can simply represent it as an array, where the index of a parent node is 

```text
public int parent(int k) {
    return (k - 1) / 2
}
```

{% hint style="info" %}
Because of the way integer division works in Java, this will always work for both parents.
{% endhint %}

We can also leave one empty spot, where the location of a parent and its children is

```text
leftChild(k) = 2k
rightChild(k) = 2k + 1
parent(k) = k/2
```

to make things simpler.  


###            

