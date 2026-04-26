- Initialised with a collection of n distinct keys. Each key is placed into its own set
- Union: combine two disjoint sets into a single set
- In-same-set: report whether keys $k_{1}$ and $k_{2}$ are currently in the same set or different sets (boolean return)
    for i in range(len(adj_list[v])):
        if adj_list[v][i][0] == u:
            adj_list[v][i][1] = 1

| Operation/Data structure | Doubly linked list | Cyclic doubly linked list | Hash table | Path compression |
| ------------------------ | ------------------ | ------------------------- | ---------- | ---------------- |
| Create                   | $O(n)$             | $O(n)$                    | $O(n)$     | $O(n)$           |
| Union                    | $O(n)$             | $O(1)$                    | $O(n)$     | $O(1)$ amortised |
| In-same-set              | $O(n)$             | $O(n)$                    | $O(1)$     | $O(1)$ amortised |

#### Path Compression and union by rank
- Create: create a tree node for each key. This yields n separate trees. The data stored in each tree node is a pointer to another tree node, initialised to NIL. Each node also contains an integer estimating the depth of the subtree rooted at itself, initialised to 0
- Chase: starting for the node for key k, follow the pointers until you reach the root of its tree. Change the pointer of each node you went through to r. This ensures that the next time we chase, we jump straight from k to r. This is path compression, and reduces the cost of walking up as it is only done fully once
- Union: $r_{a}=$ chase(a), $r_{b}=$ chase(b). If the estimated depth of $r_{a}$ is strictly greater than that of $r_b$ then change $r_b$ to point to $r_{a}$, and vice versa. If both depths are equal, make either point to the other and increment the estimated depth of the root (the one pointed to). This is union-by-rank
- In-same-set: return chase(a)==chase(b). If the roots of the trees are the same then the keys are in the same set.
All sort with $O(|E|\lg|V|)$ with Kruskal's algorithm


