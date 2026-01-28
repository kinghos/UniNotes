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

When calculating the cost, the closed form solution is ideal as it is not defined in terms of itself through calls to the $T()$ function

Substitute into itself and spot a pattern
$$\begin{align}
T &= k_{1}+k_{2}+2T\left( \frac{n}{2} \right)\\
&=k_{1}+k_{2}n+2\left( k_{1}+\frac{k_{2}n}{2}+2T\left( \frac{n}{4} \right) \right) \\
&=\dots \\
&=k_{1}(1+2+4+\dots) + k_{2}n(1+1+1+\dots)+2^{\log_{2} n}T(1) \\
&=k_{1}(n-1)+k_{2}n\log_{2} n+n \in \Theta (n\log_{2}n)=\Theta (n\log n)
\end{align}$$
The $k_1$ term above is a geometric series with $a=1,r=2,n=\log_{2}n$

An alternative method is to look at the call tree and look at each level.
The $k_2$ terms are asymptotically dominant over the $k_1$ terms
The $k_2$ terms are $k_{2}n+\frac{2k_{2}n}{2}+\frac{4k_{2}n}{4}+\dots$
which is $k_{2}n\times\text{num levels}$
The tree has $\log_{2}n+1$ levels since $\log_{2}1=0$
Hence the total cost is $\Theta (n\log n)$
_Note that an assumption was made that the array length was a power of 2. This can be dealt with using `floor` and `ceil` functions_
$T(n)=T\left( \left\lceil  \frac{n}{2}  \right\rceil \right)+T\left( \left\lfloor  \frac{n}{2}  \right\rfloor \right)+k_{1}+k_{2}n$

#### The Master Theorem
Let $a\geq1$ and 