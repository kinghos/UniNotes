#### Floyd-Warshall
Uses an adjacency matrix
For a simple path, all vertices between the start and end are defined as intermediate vertices
For any $i,j\in G.V$, consider a minimum weight path from i to j that only has intermediate vertices in a subset $\{ 1,2,\dots k \}\subseteq G.V$
Either p has k has an intermediate vertex or it does not.

for k=1 to |G.V|
	for each $i,j\in G.V$
		lookup the min weight path i to j only using verticles 1- k-1   [x]
		lookup the min weight paths i to k and k to j not including k   [y,z]
		set the min weight path i to j using 1 - k as min(x, y+z)
$O(|V|)^3$
#### Johnson's Algorithm
Solves the problem with expected running time $O(|V|^2 \log|V|+|V||E|)$
Can handle negative edge weights, detecting negative cycles and reporting no solution exists
Provided G is sparse, Johnson's algorithm is asymptomatically cheaper than Floyd-Warshall.

#### Flow Networks
Consider two vertices s and t, known as the source and sink of the flow
Two properties are needed for the edges:
- No self-loops at any vertex $\forall v\in V.(v,v)\not\in E$
- No antiparallel edges $\forall u,v\in V.(u,v)\in E\to(v,u)\not\in E$
The weights, known as capacities, are non-negative
All vertices are on some path $s\leadsto b\leadsto t$ so $|E|>|V|-1$ (every vertex other than S must have at least one inbound edge)
In other words, we can delete any vertex v if v is not reachable from s or t is not reachable from v.
A flow is a function of type $V \times V \to \mathbb{R}$
1. Flows are subject to the capacity constraint $0\leq f(u,v)\leq c(u,v)$
2. At every vertex $u\in V$ we have flow conservation
$$\sum_{v\in V}f(v,u)=\sum_{v\in V}f(u,v)$$