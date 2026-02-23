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
