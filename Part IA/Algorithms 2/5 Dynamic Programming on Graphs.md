#### Floyd-Warshall
Uses an adjacency matrix
For a simple path, all vertices between the start and end are defined as intermediate vertices
For any $i,j\in G.V$, consider a minimum weight path from i to j that only has intermediate vertices in a subset $\{ 1,2,\dots k \}\subseteq G.V$
Either p has k has an intermediate vertex or it does not.
If k is not an intermediate vertex then 