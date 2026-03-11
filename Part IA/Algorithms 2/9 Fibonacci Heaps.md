Amortised cost of $O(1)$ for all operations (except extract-min)
Eight attributes:
- Key
- Payload
- Left sibling pointer
- Right sibling pointer
- Parent pointer
- Child pointer (to ONE child)
- Degree (num children)
- Marked flag

A reference to the root of a Fib Heap is a 2-tuple `(r,n)`
- r is a pointer to the node containing a current minimum key
- n is the number of keys currently present in the Fib Heap
It is permitted to keep pointers to nodes within the heap structure
Creation initialises the heap as `(nil, 0)`
