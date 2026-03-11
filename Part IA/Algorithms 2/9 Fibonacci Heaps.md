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
where $\phi=\frac{1+\sqrt{ 5 }}{2}$ (the golden ratio) and n is the number of nods after removing the minimum.
Indexing from 0:
```
Going through the root list with node t:
if A[t.degree] == NIL
	A[t.degree] = t
else
	old_start = start
	old_start_right = start.right
	merge(t, A[t.degree])
	if (old_start.parent != NIL)
		start = old_start_right
```

Merge:
```
if a.key >= b.key
	A[b.degree] = NIL
	b.degree = b.degree + 1
	a.left.right = a.right
	a.right.left = a.left
	a.left = a.right = a
	if (b.degree == 1)
		b.child = a
	else
		DLL-splice(b.child, b.child.left, a, a.right)
	if (A[b.degree] != NIL)
		merge(b, A[b.degree])
	else
		A[b.degree] = b
else
	repeated but for b instead of a
```

Insert is only $O(1)$ because it does half the work - inserting an item to the root list leaves extract-min to deal with it later.
