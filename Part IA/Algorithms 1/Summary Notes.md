Recurrence relations - substitution method, or draw out the tree, starting with the $\Theta$part and branching off into the recursive and other $\Theta$ parts

Master theorem - what you are looking for is which is polynomially larger - $n^{\log_{b}a}$ or $f(n)$. If they are of the same order, then $T(n) \in \Theta(n^{\log_{b}a} \lg n)$

#### Algorithms

##### Quicksort
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