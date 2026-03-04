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
