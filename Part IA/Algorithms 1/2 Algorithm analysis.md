Consider
- Memory requirements (space complexity)
- CPU time (time complexity) 
- Disk operations
To measure these, we need to measure the size of an input instance succinctly
in some cases operations that may seem to take constant time may take longer, e.g. finding the length of an array - sometimes the length may be beyond the integer limit, in which case the value will be stored with arbitrary precision arithmetic (where numbers are arrays of digits)

Considerations from pseudocode:
- Memory cells e.g. elements in an array, can only hold one item
- Indexing an array takes 1 unit of time
- Arithmetic operations take 1 unit
- Comparisons take 1 unit
- Assignments to variables take 1 unit

#### Cost of insertion-sort
![[InsertionSortCost.png]]
The running time, $T(n)$, on inputs of size n is the cost of each line multiplied by the number of times the line is executed.

Best case: $T(n)=an+(b+c+g)(n-1)+d\sum^n_{j=2}t_{j}+(e+f)\sum^n_{j=2}(t_{j}-1)$
This is when the data is in sorted order, i.e. $t_{j}=1$
This leaves a linear time complexity of $O(n)$
In the worst case, the data is in reverse sorted order, meaning each while loop performs $j-1$ iterations, meaning $t_{j}=j$ and $O(n^2)$ complexity.
The average case is similarly $O(n^2)$.

Usually we want the worst case running time/memory consumption
- It gives an upper bound, so sufficient resources can be provided
- The worst case may occur quite often
- The average case is often the same as the worst case

#### Order of growth
$\Theta(g(n))$ is the set of functions f(n) such that there exist positive constants $c_{1}, c_{2}$ and $n_0$ such that $0\leq c_{1}g(n)\leq f(n)\leq c_{2}g(n)$ for all $n>n_{0}
$g(n)$ is an asymptotically tight bound for $f(n)$. This means, within a constant multiplicative factor.
e.g. if the true cost is $10.3n^2 + 6.1n - 0.4$, then we can write $\Theta(n^2)$ but not $\Theta(n^4)$ or $\Theta(n)$

$O(g(n))$ is the set of functions, $f(n)$ such that there exist positive constants $c$ and $n_0$ such that $0 \leq f(n)\leq cg(n)$ for all $n\geq n_0$
$g(n)$ is an asymptotic upper bound for $f(n)$
$\Theta(g(n))\subseteq O(g(n))$
e.g. e.g. if the true cost is $10.3n^2 + 6.1n - 0.4$, then we can write $\Theta(n^2)$ and $\Theta(n^4)$ but not $\Theta(n)$

$\Omega(g(n))$ is the set of functions, $f(n)$ such that there exist positive constants $c$ and $n_0$ such that $0 \leq cg(n)\leq f(n)$ for all $n\geq n_0$
$g(n)$ is an asymptotic lower bound for $f(n)$

Little-o and little-omega denote asymptotically non-tight versions of their big counterparts.

##### Properties
Transitivity - all four
Reflexivity - $\Theta, O, \Omega$
Symmetric - $\Theta$

#### Divide and conquer sorting
Insertion sort is an incremental algorithm - it builds a sorted version of the subarray `A[1..j-1]`, and inserts `A[j]` into the correct place to build `A[1..j]`.
Another technique is divide and conquer
1. Divide the original problem into two or more smaller instances of the same problem
2. Conquer the subproblems by calling the same function recursively on each of them in turn
3. Combine the solutions to the subproblems to build the solution to the original problem
