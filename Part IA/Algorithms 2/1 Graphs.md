- A graph $G=(V,E)$ is a set of vertices and edges $\subseteq V \times V$. We usually care about finite graphs.
- In an undirected graph, the edges are unordered pairs (or E is symmetric); directed graphs have ordered pairs of vertices in the edge set.
- A weighted graph has a function $E \to \mathbb{R}$ that associates a weight with each edge.
- A graph is fully connected if $E = V \times V$

E can be represented in two ways: adjacency lists and matrices
- A $|V| \times |V|$ adjacency matrix, M is $O(|V|^2)$ size. If G is unweighted, $M_{u,v}=1$ if $(u,v) \in E$ and 0 otherwise. In weighted graphs, $M_{u,v}$ holds the weight of the corresponding edge. If G is undirected, we only need to store the upper or lower triangle of $M$
- Adjacency lists are stored in an array of length $|V|$ where $A[u]$ stores a pointer to a linked list of the vertices $v \in V$ such that $(u,v) \in E$. If G is weighted, the lists store tuples $(v,w)$ such that $(u,v) \in E$ and weight $(u,v) =w$

| Matrices                                  | Lists                                      |
| ----------------------------------------- | ------------------------------------------ |
| Compact for dense graphs                  | Compact for sparse graphs                  |
| O(1) to check if edge exists              | O(\|V\|) to check if edge exists           |
| O(\|V\|) to list neighbouring nodes       | O(num neighbours) to list neighbours       |
| Can halve storage if G is undirected      | Cannot halve storage for undirected graphs |
| $O(\|V\|^2)$ to iterate through all edges | O(\|E\|) to iterate through all edges      |
- The transpose of a directed graph is a graph which has all the directed edges reversed. This is achieved by transposing the edge matrix
- The in-degree and out-degree of a vertex are the numbers of incoming and outgoing edges, and the degree of a vertex is the number of edges incident at that vertex
- The square of a graph is the graph in which an edge (u,v) is present if there is a path between u and v in the original graph consisting of at most two edges
- Edges are adjacent if they share a vertex

- A complete graph is fully connected ($E=V \times V$)
- A connected graph is one where every pair of vertices are connected by at least one path
- An induced subgraph is another graph where $V' \subseteq V$ and $E'$ is that subset of $E$ consisting of all edges $(u,v)\in E$ where $u,v \in V'$
- A clique within a graph G is any induced subgraph that is complete
- The complement graph is the graph with edges not in E
- A graph is acyclic if no vertex can be reached by a path from itself

- Vertex colouring is the task of assigning colours to each $v \in V$ such that no adjacent vertices have the same colour
- Edge colouring is the task of assigning colours to each edge $e \in E$ such that no adjacent edges have the same colour
- Face colouring is the task of assigning colours to each face of a planar graph such that no adjacent faces have the same colour. A planar graph can be drawn on a plane such that no two edges intersect. A face is a region bounded by edges (including the infinite-area region around the outside).

#### Breadth First Search
BFS can be used on directed and undirected graphs
On a graph it is slightly more complex than on a tree, because we have to worry about duplicate discoveries of a vertex

