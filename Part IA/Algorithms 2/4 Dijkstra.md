#### Optimal Substructure
Any subpath within a path must be the shortest path between those two nodes.

### Dijkstra
Dijkstra uses a greedy approach to exploit optimal substructure of shortest paths.
It works on directed graphs with non-negative edge weights.
Correctness is proved via induction on the cardinality of set S.
$$\phi:v.d= \delta(s,v).\forall v\in S$$
At the start of the first iteration, $S=\emptyset$ so $\phi$ is vacuously true

