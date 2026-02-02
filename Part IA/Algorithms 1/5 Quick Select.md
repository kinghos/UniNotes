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
This can be further optimised by using minimum and maximum functions when the pivot is in position $i-1$ or $i+1$ respectively.
Worst case:
$$\begin{align}
T(1)&=1 \\
T(n)&=T(n-1)+kn
\end{align}$$
This leads to a cost of $\Theta(n^2)$
Other standard improvements include:
- Randomising input data
- Taking out all values equal to the pivot
	- Lots of values equal to the pivot means it is likely that the same pivot will be selected again (and be the smallest/largest value) leading to inefficiency
- Picking the pivot randomly
- Median-of-three pivot
	- Pick three items, and take the median. This reduces the chance that you pick the largest or smallest element as the pivot.

 
 Median-of-medians pivot
	
#### Median-of-medians pivot
- Change partition to work as follows:
	- Split subarray into groups of 5
	- For each group of 5, find the median of those groups
	- Find the median of those medians using quick select, and use it as the pivot

The median is considered to be the value in position $\frac{n+1}{2}$ when in sorted order. For an even n, we consider the lower median and upper median, on either side of the halfway point.
The final pivot is the median of the $\left\lceil  \frac{n}{5}  \right\rceil$ medians. Half of the medians must be greater than the pivot, and for each median greater than the pivot, two of the five in its group are greater.
This leads to quick select being $\Theta(n)$

