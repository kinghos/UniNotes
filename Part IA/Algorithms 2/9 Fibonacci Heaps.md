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
Collection of binomial min-heaps, held unordered in a doubly linked cyclic list
If a node's key is decreased and becomes smaller than the parent's key then it violates the heap property and cannot remain in its current place in the heap

For a 1-item fib heap:
- Key = k
- Payload = p
- Left = this
- Right = this
- Parent = NIL
- Child = NIL
- Marked = false
- Degree = 0

Insertion is done with a destructive union
When extracting the minimum, the new minimum key has to be one of the children of the old minimum, or one of the other keys in the root list.

To clean up the array after extracting the minimum an array is needed with size
$$D(n)+1=\lfloor \log_{\phi }n \rfloor +1 $$
where $\phi=\frac{1+\sqrt{ 5 }}{2}$