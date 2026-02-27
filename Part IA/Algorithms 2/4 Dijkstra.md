#### Optimal Substructure
Any subpath within a path must be the shortest path between those two nodes.

### Dijkstra
Dijkstra uses a greedy approach to exploit optimal substructure of shortest paths.
It works on directed graphs with non-negative edge weights.
Correctness is proved via induction on the cardinality of set S.
$$\phi:v.d= \delta(s,v).\forall v\in S$$
At the start of the first iteration, $S=\emptyset$ so $\phi$ is vacuously true

The cost of Dijkstra depends on the type of priority queue used. Initialisation of the queue varies between $O(1)$ and $O(|V|)$

For an array/hash table implementation, the final cost is 
$O(|V|1+|V||V| +|V|1+|E|1)=O(|V|^2+|E|)$
(initialisation + extractions + empty checks + decrease keys)

With a min heap, the final cost is 
$$O(|V|+|V|\log|V|+|V|1+|E|\log|V|)=O((|V|+|E|)\log|V|)$$
If every vertex is reachable from s, this is $O(|E|\log|V|)$

#### All-Pairs Shortest Paths
Input: a weighted graph
Ouptut: a $|V|\times|V|$ matrix $D=d_{ij}$, where $d_{ij}=\delta(i,j)$ is the shortest path weight from i to j.
Repeating Bellman-Ford for every vertex yields a complexity of $O(|V|^2|E|)$ time.
If there are non-negative edge weights, Dijkstra can be used, achieving $O(|V|^2\log|V|+|V||E|)$

##### Matrix methods
Taking the square matrix of edge weights, consider the square of this matrix. However, change the addition operation to MIN, and the multiply operation to addition. In other terms, add corresponding terms in each matrix and then find the minimum of that row/column sums.
Repeated squaring will give the solution in $O(|V|^3\ln|V|)$
