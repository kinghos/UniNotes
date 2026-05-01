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

Line 5: `C[i]` holds the number of instances of value i in the input array
Line 7: `C[i]` holds the number of elements less than or equal to i
Lines 9 and 10 put the data into the correct order in the output array. Line 10 makes sure if elements aren't distinct they are ordered consecutively.
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

#### Cost of radix-sort
To sort n numbers of d digits each, where each digit can take on one of k different values, radix sort is $\Theta(d(n+k))$
Each stable sort is applied to n keys using a key range of `[0..k-1]`. Counting sort is the obvious way to achieve that, taking $\Theta(n+k)$ time each.

### Bucket sort
```
let n = A.length, B = new Array[0..n-1]
for i = 0 to n-1
	B[i] = empty_list
for i = 1 to n
	insert A[i] into list B[floor(n*A[i])]
for i = 0 to n-1
	insertion-sort(B[i])
concatenate B[0], B[1], ... B[n-1]
```

#### Cost of bucket sort
All the steps are trivially linear except the calls to insertion sort. It turns out that the complexity is $\Theta(n)$
![[SortingSummary.png]]