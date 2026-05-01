The (binary) heap is a data structure. It can be thought of as a binary tree (**not a search tree!!**), or as an array.

Properties of min-heaps/max-heaps:
- Structural property: Considered as a tree, a heap is a full tree except possibly for the lowest level which is filled from left to right
- Ordering property: in a min-heap, every node holds a lesser-or-equal key than its children; in a max-heap, nodes have greater-or-equal keys than their children
The tree is assembled by essentially reading across the array and putting into the tree.
![[HeapStructure.png]]
In the array model, for a root `A[i]`, the left child will be at `2i` and the right child at `2i+1`. This means the array representation uses less memory as it does not use pointers, but takes more CPU cycles (though this is negligible)

Heaps are semi-structures, which are cheaper to build than fully-structured data structures.
This is because of the partial sort order:
- The smallest item is in only one place: the root
- The second smallest is in one of two places (one of the root's children)
- The third smallest is in one of three places (root's other child, or either child of the second smallest)
Semi-structures support operations to change the heap cheaply, and maintain all the properties of the semi-structures
- `max-full-heapify` in $O(n)$ time, `max-heapify` in $O(\log n)$ time
- `max-peek` in $O(1)$ time
- `max-insert`, `max-extract`, `increase-key` in $O(\log n)$ time
Symmetrically, but with `decrease-key` for min-heaps

#### Max-Reheapify
Max-reheapify assumes that everything below node `i`, in its left and right children (if they exist) are valid max-heaps
Its purpose is to build a single, large, max-heap out of two existing max-heaps and one extra key.

- Compare the new key to the roots of the two existing heaps
- If the new key is the largest, we're done
- If not, swap with the larger of the two sub-heap roots and recurse on the node you swapped with.
![[MaxReheapify.png]]
```
def max_reheapify(A, i)
	l = 2i
	r = 2i + 1
	largest = (l <= A.heap_size && A[l] > A[i]) ? l : i
	if (r <= A.heap_size && A[r] > A[largest]) largest = r
	if largest != i
		swap(A[i],A[largest])
		max_reheapify(A, largest)
```

#### Max-full-heapify
Max-full-heapify notes that the bottom-level leaves are valid max-heaps.
It calls max-reheapify on the last node that has at least one child then works its way back up to the root. This turns any array into a valid max-heap
```
def max-full-reheapify(A)
	A.heap_size = A.length
	for i = floor(A.length/2) downto 1
		max-reheapify(A, i)
```
![[MaxFullReheapify.png]]
#### Max-extract
The largest key in a max-heap is the root. To extract the max we cannot simply remove it without violating the structural property of a heap.
The only key that can be removed safely is the rightmost key on the bottom row. By swapping this with the root, and reducing the heap size by 1, the root can be extracted. Max-reheapify can be called at the root to fix the structure. This has a cost of $O(\log n)$
The same follows for min-extract

#### Heapsort
```
def heapsort(A)
	max_full_heapify(A)
	for i = A.length downto 2
		swap(A[1], A[i])
		A.heap_size = A.heap_size - 1
		max_reheapify(A,1)
```
Essentially, calling max-reheapify sorts the array as a heap, and then the largest element is extracted and stored at $i$, which sorts A into ascending order.
