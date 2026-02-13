#### Rooted Trees
A rooted tree has a single entry point, the root.
- Binary trees hold one data item, pointers to two children, and optionally a pointer to the parent node.
- Trees cannot have cycles
- Trees cannot have multiple paths to the same node
Sometimes children need to be added and removed from tree nodes while an algorithm runs. We cannot have a fixed number of child pointers, so we use a linked list of children as required.

#### Binary Search Trees
- The data is a (key, payload) tuple
- The key in node `i` is strictly greater than all the keys in its left subtree
- The key in node `i` is strictly less than all the keys in its right subtree
- Any kind of search tree does not allow duplicate keys.
- Supported operations include insert, delete, search, predecessor, successor, minimum, maximum, all in $O(\log n)$ time
- 