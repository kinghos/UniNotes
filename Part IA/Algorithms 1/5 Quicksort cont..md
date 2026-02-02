Splitting the array into a different ratio to 1:1 does not change the complexities. This shows that you should aim for a ratio split with divide and conquer algorithms as they are performant.

The worst case for quicksort occurs when the pivot is the largest or smallest element in the array. The recurrence forms an arithmetic progression finalising as $\Theta(n^2)$
Splitting n keys in to $[x,1 \text{ pivot}, (n-x-1)]$ for any constant x gives the same outcome. This shows that divide and conquer algorithms should avoid splitting off constant size subproblems.

#### Quick Select
The $i^{th}$ order statistic is the $i^{th}$ smallest value in a set of n elements. Finding it is known as the selection problem.

```
if p == r
	return A[p]
q = partition(A, p, r)
k = q - p + 1
if i == k
	return A[q]
else if i < k return quickSelect(A, p, q-1, i)
else return quickSelect(A, q+1, r, i-k)
```
Using the pivot guarantees that you narrow down the region that the $i^{th}$ element lies in.
This