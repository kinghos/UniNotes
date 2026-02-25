#### Edge properties
- Every edge in an undirected graph is either a tree edge or a back edge
- An edge $(u,v)\in G.E$ is a tree edge or forward edge iff `u.discovertime < v.discover_time < v.finish_time < u.finishtime`
- An edge is a back edge iff `v.discover_time <= u.discover_time < u.finish_time, v.finish_time`
- An edge is a cross edge iff `v.discover_time < v.finish_time < u.discover_time < u.finish_time`

Topological sort - an ordering of a set of things to order, that follows a set of constraints

#### Strongly Connected Components problem
Input: a directed graph $G=(V,E)$
Output: the strongly connected components of $G$
A strongly connected component is a maximal set of vertices $C \subseteq V$ such that for all $u,v \in C$ we have both that $v$ is reachable from $u$ and that $u$ is reachable from $v$ using edges in $E$
This algorithm uses the transpose graph $G^T=(V,E^T)$
1. Run DFS on G to populate the `finish_time` for each vertex $v \in G.V$
2. Compute $G^T$ 
3. Run DFS on $G^T$ but in the main loop of DFS call DFS-helper on vertices in order of descending finish_time as computed in step 1
4. For each tree in the forest produced by $DFS(G^T)$, output the vertices as a separate strongly connected component of G

#### Shortest Path Problems
Input: A directed, weighted graph $G=(V,E)$ with its weight function $w:E\to \mathbb{R}$
We define the weight of a path $p=v_{0},v_{1},v_{2},\dots,v_{k}$ as the linear sum of the edge weights:
$w(p)=\sum^k_{i=1}w(v_{i-1},v_{i})$
The edge weights can represent any additive metric

The shortest path weight is $\infty$ if there is no path from u to v, and otherwise it is $min_{p}(w(p))$, where the minimisation over p considers all paths $u \leadsto v$

Single-Source Shortest Paths: Find the shortest paths through a directed, weighted graph from a specified source to all destinations

##### Complications
- Negative-weight edges and cycles
- Zero-weight cycles - make sure to exclude these cycles

#### Bellman-Ford
Finds shortest paths from every vertex in the graph that is reachable from s (SSSP) in $O(|V||E|)$ time
It returns false if it finds a negative weight cycle, otherwise true. All paths are acyclic (excluding zero-weight cycles)


