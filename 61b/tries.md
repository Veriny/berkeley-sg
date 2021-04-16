# Tries

Tries are a way that we can store string keys in a map. A trie is a tree with the following properties.

* Each node in the tree contains a letter.
* Each node can be stored by multiple keys.
* Each node stores whether it is the end of a key or not.

When finding keys in a trie, we just go letter by letter until we're out of letters in the key we are inquiring — hitting a blue node at the end is a hit, while falling off the tree or ending on a white node is a miss.

## Implementation

The basic trie implementation from lecture is as follows.

```text
public class TrieSet {
    private static final R = 128;
    private Node root;
    private static class Node {
        private boolean isBlue; //Whether this is the end of a key
        private DataIndexCharmap next;
        private node (boolean isBlue, int R) {
            this.isBlue = isBlue;
            next = new DataIndexedCharMap<Node>(R); 
        }
    }
}
```

### Runtime

Runtime is independent of the number of keys!

## Alternate DataIndexedCharacterMaps

The goal is to make our DataIndexedCharMap as efficient and space efficient as possible.  For example, we can use a HashTable, or a balanced BST. 

