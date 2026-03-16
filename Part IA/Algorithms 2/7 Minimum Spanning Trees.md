The total cost of finding augmenting paths is $O(|V||E|)$

#### Hopcroft-Karp
```
let M = empty-set
do
	a[] = all-vertex-disjoint-shortest-augmenting-paths(G, M)
	M = M XOR a1 XOR a2 XOR ... XOR a(a.length)
while (a.length != 0)
return M
```
All-Vertex-Disjoint-Shortest-Augmenting-Paths finds the minimum length augmenting paths for M
$O(|E|\sqrt{ |V| })$ time
A maximum matching is a largest cardinality subset of non-adjacent edges in an input graph
A maximal matching is a subset of non-adjacent edges that cannot be extended

#### Minimum Spanning Trees
Input: A connected undirected graph with a weight function
Output: An acyclic subset $T\subseteq E$ that connects all the vertices and whose total weight is minimal, where $w(T)=\sum_{(u,v)\in T}w(u,v)$
T must be a tree but not necessarily rooted. T is a rooted tree. A minimum spanning tree is a spanning tree with minimum total edge weights, and need not be unique

These can be computed by having a set A of edges, and each time an edge is added (a safe edge) it maintains the property that $A \subseteq T$

#### Kruskal's Algorithm
Finds safe edges to add to a growing forest of trees by finding least weight edges that connect any two trees in the forest
Sort edges in ascending order, scan - check each edge, check if two are already connected (can be done with a disjoint)

#### Prim's Algorithm
Maintains that A is a single tree and adds safe edges between the tree and an isolated vertex, to increase the size of the tree until $A=|V|$. Resembles Dijkstra