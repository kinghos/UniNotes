The measure of input size is the length of the region to be sorted, $n=r-p+1$
Let $T(n)$ be the cost of solving a problem of size n using merge sort
When p=r the algorithm stops immediately, $T(1)=1$
When $p<r$ the algorithm:
- Calculates q, which is $\Theta(1)$ work
- Calls itself on two problems of size at most $n/2$: 2x $T\left( \frac{n}{2} \right)$
- Calls `merge(A,p,q,r)` - calling the cost `m(A,p,q,r)`
	- Creates and fills two arrays of total length n=2
	- Loops from k=p to r
		- Assigns into an array position - constant cost
		- Adds one to either i or j - constant cost
- Total cost of `m` is $\in \Theta(n)$
- $M(A,p,q,r)=k(r-p+1)$ for some $k>0$ for all $n>n_0$

When calculating the cost, 