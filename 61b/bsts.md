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

## 2-3 Trees

In order to prevent BSTs from becoming too "spindly" \(too little elements relative to height, which makes time complexity more similar to a linked list\).

2-3 trees are just binary search trees, but nodes can be crammed with more than one item.  If a node gets too full, just pass one of the items in the overstuffed node to the parent node. Then, split the nodes up \(if there are two items in the parent, have three children one node with the things that are less than both, one for in between, and one for items that are greater than both\)

## LLRB Trees

LLRB trees mimic 2-3 trees, but without the complication of overstuffing nodes. Here is how it works.

* When inserting, use red link.
* No node may have two red links
* Every path from the root to the leaf must have the same number of black links.
* When inserting, use a red link.
* If there is a right leaning red link, rotate left the parent node to fix it.
* If there is are two consecutive left links, rotate the top node right to fix.
* If there are any nodes with two red children, color swap \(every link the node is connected to changes color\) the node. The root's parent link will always be black.

