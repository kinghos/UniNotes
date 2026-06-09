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
- Predecessor and successor require parent pointers

For deleting items:
- If the node has no children, remove it from its parent
- If it has one child, reparent the child with this node's parent
- If it has two children, replace d's (key, payload) with that of d's predecessor, then delete the predecessor node (which can have at most one child)
	- Think of this as finding two adjacent elements, swapping them and deleting one - this retains the order

#### Balanced Trees
BSTs have average-case $O(\log n)$ performance but the worst case is $O(n)$ when every tree node has exactly one child.
To achieve $O(\log n)$ in the worst case, we need to ensure that our trees remain balanced, regardless of the order in which keys are inserted or deleted.

B-trees are made of leaf nodes and internal nodes. Leaf nodes hold no keys or payloads, Internal nodes hold varying numbers of keys and payloads.
A B-tree of minimum degree T, has five defining characteristics:
- Internal nodes must hold at least $T-1$ keys and payloads (except the root)
- Internal nodes can hold at most $2T-1$ keys and payloads (including the root)
- A node with $t$ keys must have $t+1$ children
- Keyless leaves all exist at the same depth below the root
- The keys in any internal node divide the ranges of keys in their children (generalising the binary search tree property)
Consider each pointer to a child as being between keys in the B-tree
Because tree algorithms depend on the height of a tree, we want an
upper bound on the height of a B-tree with N keys. The number of levels required to hold N keys is at most $O(\log n)$
It is not permitted to maintain pointers to any internal nodes.