- Certain nodes are most crucial in linking densely connected regions of the graph, known as gatekeepers. Cutting those edges isolates cliques/clusters
#### Betweenness centrality
Betweenneess centrality of a node V is defined in terms of the proportion of shortest paths that go through V for each pair of nodes.

#### Brandes Algorithm
- Optimal substructure property
- Overlapping solutions property
$\sigma(s,t|v)$ is the number of shortest paths between s and t that pass through v
Betweennesss centrality is 
$$C_{B}(v)=\sum_{s,t\in V}\frac{\sigma(s,t|v)}{\sigma(s,t)}$$
Brandes algorithm iterates all vertices s in V, and calculates $\delta(s|v)$ for all $v\in V$ in two phases: breadth first search, then visiting vertices in reverse order aggregating dependencies according to equation
