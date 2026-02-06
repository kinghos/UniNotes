#### Cost of Max-full-heapify
Best case:
- The initial array order is compatible with the heap ordering property
- Max-full-heapify considers about n/2 keys, performs 2 comparisons per key but no swaps and no recursive calls - $\Theta(n)$
Worst case:
- Occurs when every comparison results in a swap and every recursive call also results in a swap and another recursive call.

#### Cost of Heapsort
$O(n\log n)$

#### Sorting in linear time
If something is known about input data, time complexity can be better than $\Omega(n\log n)$
1. Counting sort - n inputs in the range `[0..k]` where $k\in O(n)$
2. Radix sort - sorting d-digit numbers
3. Bucket sort - sorting data that is uniformly distributed over $[0,1)$

### Counting sort

```
let C = new Array[0..k]
for i = 0 to k
	C[i] = 0
for j = 1 to A.length
	C[A[j]] = C[A[j]] + 1
for i = 1 to k
	C[i] = C[i] + C[i-1]
for j = A.length downto 1
	B[C[A[j]]] = A[j]
	C[A[j]] = C[A[j]] - 1
```
A: input data
B: array into which the output is written
k: top limit of the range of values
`C[i]` holds the number of instances of value i in the input array
#### Cost of counting sort
Initialising the C array takes $\Theta(k)$ time
Counting items in the A array takes $\Theta(n)$ time
Converting the count of key i to the index of the last instance of i in the output takes $\Theta(k)$ time
Populating the output takes $\Theta(n)$ time
Overall $\Theta(k+n)$

### Radix-sort
```
for i = 1 to d
	sort array A on digit i with any stable sort
```
where 1 is the least significant digit
#### Stable sorts
A stable sort guarantees to preserve the order of inputs when their sort keys are equal. This is useful if you want a secondary sort key, e.g. sort exam results by mark, but then if they have the same mark sort by alphabetical order. This is a sort by name first, then a stable sort by mark. This will preserve the sorting by name.

