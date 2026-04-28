#### Partitioning
Partitioning reorders a list by placing items smaller than the pivot to the left of the pivot, and items larger than the pivot to the right of the pivot.

```
def quicksort(A, p, r)
	if p < r:
		q = partition(A, p, r)
		quicksort(A, p, q-1)
		quicksort(A, q+1, r)

def partition(A, p, r)
	x = A[r]
	i = p - 1
	for j = p to r - 1
		if A[j] <= x
			i = i + 1
			swap A[i], A[j]
	swap A[i+1], A[r]
	return i+1
```

##### Proof
To prove that `partition` works, it must:
1. Rearrange the elements of `A[p..r]` into two (possibly empty) subarrays `A[p..q-1]` and `A[q+1..r]` such that
	a. Each element of `A[p..q-1]` is less than or equal to `A[q]`
	b. `A[q]` is less than or equal to each element of `A[q+1..r]`
2. Return q

Can look for a loop invariant property (checking initialisation, maintenance, termination)
Let P = at the beginning of each iteration of the for loop, for any array index k:
1. If $p\leq k\leq i$ then $A[k]\leq x$ (region known to be < pivot)
2. If $i+1\leq k\leq j-1$ then $A[k]>x$ (region known to be > pivot)
3. If $k=r$ then $A[k]=x$ (ensures pivot exists)
