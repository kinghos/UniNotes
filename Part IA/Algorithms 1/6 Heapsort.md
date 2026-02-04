The (binary) heap is a data structure. It can be thought of as a binary tree, or as an array.

Properties of min-heaps/max-heaps:
- Structural property: Considered as a tree, a heap is a full tree except possibly for the lowest level which is filled from left to right
- Ordering property: in a min-heap, every node holds a lesser-or-equal key than its children; in a max-heap, nodes have greater-or-equal keys than their children
The tree is assembled by essentially reading across the array and putting into the tree.
![[Pasted image 20260204101758.png]]
In the array model, for a root `A[i]`, the left child will be at `2i` and the right child at `2i+1`. This means the array representation uses less memory as it does not use pointers, but takes more CPU cycles (though this is negligible)
