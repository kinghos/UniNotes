#### Single-Source All-Destinations Shortest Paths
Consider:
- An unweighted graph, directed or undirected
- The concept of "shortest" means fewest edges
- Single source, taken as input
- We want path lengths and actual paths
- and we want this for every destination
For the source, distance = 0 and path = `[]`
Unreachable vertices have distances of $\infty$

The total cost of this algorithm is $O(|V|+|E|)$
Breadth-first tree - all vertices and edges reachable by breadth first search

### Depth First Search
Let "time" be a global clock that effectively numbers events in exploration order.
The running time is $\Theta(|V|+|E|)$

An edge is a tree edge if the destination vertex was discovered by taking this edge
An edge is a back edge if it connects a node to an ancestor
An edge is a forward edge if it connects a node to a descendant
All other edges are cross edges