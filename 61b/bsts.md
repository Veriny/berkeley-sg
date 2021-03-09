# Trees

## Tree review from 61A

A tree has:

* A set of nodes
* A set of edges that connect the nodes
* Between any two nodes, there may only be one path.
* Each node has a parent node and any number of child nodes.

  * If the tree is a binary tree, each parent can have at most two children.

## Binary Search Trees

A binary tree is also a binary search tree if it has the following properties.

1. Its left child has a value that is less than its value.
2. Its right child has a value that is more than its value

{% hint style="info" %}
Because of the above constraints, a binary tree may not contain duplicate values.
{% endhint %}

### BST Insertion

Insertion is achieved by searching for the key you want to insert. If you find it, it means that it is already in the tree and can't be added, so do nothing. If you don't, wherever you end up after traversing the tree you can add the node.

### BST Deletion

If the victim node has no children, just disconnect the link from its parent and it will be garbage collected.

If the victim node has one child, connect the victim's parent to the victim's child, and unlink the victim.

This leaves us with the final case, in which the node we want to delete has two children. In this case, it is a bit more difficult. We need to find a new node to be the root node of the node's subtree. This root node must meet the conditions that it is greater than everything in the left subtree and smaller than everything in the right subtree. The node that has these properties are either the **predecessor** or **successor.** This process is called **Hibbard deletion.** Predecessor refers to the largest item that is smaller than the key, and the successor refers to the smallest item that is larger. We delete the node that we choose, and then replace its value with the root node.

{% hint style="success" %}
TODO: 2-3 Trees, LLRB trees, rotation
{% endhint %}

