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
