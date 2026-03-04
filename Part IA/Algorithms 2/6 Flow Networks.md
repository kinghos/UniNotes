The value of a flow is defined as
$$|f|=\sum_{v\in V}f(s,v)-\sum_{v\in V}f(v,s)$$
Second term is usually zero as there is no flow into the source, but the networks will be generalised to include ones where edges into the source will not always have zero weight

#### Maximum Flow Problem
Antiparallel edges can be handled by introducing additional vertices to split one of the edges. Two new edges are assigned the same capacity as the original they replace.
![[AntiparallelFlow.png]]
If we want to model a system where flow originates from multiple sources and is consumed by multiple sinks we can add additional vertices and edges:
- Two additional vertices for the supersource s and supersink t
- Edges (s, $s_i$) for i=1 to m and ($t_j$, t) for j = 1 to n all with capacity $\infty$
This reduces the multiple source multiple sink problem to the single source, single sink problem.
![[SuperSource.png]]
Given a flow network $G$, and a flow $f$, the residual network contains residual edges showing how we can change the flow.
1. if an edge $(u,v) \in E$ and $f(u,v)<c(u,v)$ then we can add more flow to the edge
2. If $f(u,v)>0$ then we can cancel flow that is already present by adding flow in the reverse direction, up to $f(u,v)$ along edge $(v,u)$

Any flow $f'$ in the residual network $G_f$ can be added to the flow to make a valid flow because the flow assigned to every edge cannot exceed its capacity and cannot become negative. This is augmentation, written as $f\uparrow f'$
$$|f\uparrow f'|=|f|+|f'|$$
An augmenting path is a simple path from s to t in the residual network.
The maximum amount by which we can increase the flow along each edge in p is called the residual capacity of the path p.
##### Ford-Fulkerson
```
initialise flow f to 0 on all edges
while there exists an augmenting path in p the residual network G
	augment the flow f along p
return f
```

A cut of a flow network is a partition of V into S and T = V \ S such that $s \in S,t \in T$
Net flow across the cut is
$$f(S,T)=\sum_{u\in S}\sum _{v\in T}f(u,v)-\sum _{u\in S}\sum_{v\in T}f(v,u)$$
In other words, $f(S,T)=|f|$
A minimum cut is a cut whose capacity is minimum over all cuts of the network.

#### Max-Flow Min-Cut Theorem
If f is a flow in a flow network, with source s and sink t, then the following conditions are equivalent:
1. f is a maximum flow in G
2. The residual network $G_f$ contains no augmenting paths, and
3. $|f|=c(S,T)$ for some cut $(S,T)$ of G.
Can be proved with a cyclic proof $1\implies 2 \implies 3 \implies 1$
