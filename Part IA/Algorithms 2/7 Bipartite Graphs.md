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
