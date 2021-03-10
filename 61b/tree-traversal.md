# Graphs, Tree Traversals

## Depth First Traversals

### "Preorder" Traversal

In this kind of traversal, we "visit" a node, and then traverse its children. From lecture, we have the following code for that.

```java
void preOrder(BSTNode x) {
    if (x == null) return;
    print(x.key); //"Visiting" the node
    preOrder(x.left); //Traversing its children.
    preOrder(x.right); 
}
```

### "Inorder" Traversal

Here, we traverse left child, visit, then traverse right child.

```java
void inOrder(BSTNode x) {
    if (x == null) return;
    inOrder(x.left); //Traversing its children.
    print(x.key); //"Visiting" the node
    inOrder(x.right); 
}
```

### "Postorder" Traversal

Traverse both children, and then visit the node.

```java
void postOrder(BSTNode x) {
    if (x == null) return;
    postOrder(x.left); //Traversing its children.
    postOrder(x.right); 
    print(x.key); //"Visiting" the node
}
```

{% hint style="info" %}
Visual trick for humans: Trace a path around the graph, from the top going counter-clockwise, and:  
Preorder traversal: Visit every time we pass the left of a node.  
Inorder traversal: Visit when we cross the middle of a node.  
Postorder: Visit when we cross the right of a node.
{% endhint %}

