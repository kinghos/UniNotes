#### Directed graphs
A directed graph $(A,R)$ consists of a set A and a relation R on A (i.e. a relation from A to A). We write $Rel(A)$ for the set of relations on a set A; that is $Rel(A)=\mathcal{P}(A\times A)$

##### Matrix addition
$(M\oplus N)_{i,j}=M_{i,j}\oplus N_{i,j}$
The zero matrix has no effect in the semiring.

$x\ R\ y$ means "there is an edge from $x$ to $y$"
Directed graphs are written as the pair of a set and a relation. e.g.
$$(\{ x,y,z \},\{ (x,y) \})$$
is the graph of three vertices and an edge between $x$ and $y$

$R^{\circ n}:A\mapsto A$
$R^{\circ{0}}=\text{id}_{A}$
$R^{\circ(n+1)}=R\circ R^{\circ n}$
This composition will produce lengths of increasing lengths, e.g. if $(A,R)$ has the path $x\to y\to z$ then $(A,R^{\circ2})$ will compose the edges and form a path of $x\to z$, i.e. it will form paths of length 2 in the original graph.

The path relation on $R:A\mapsto A$ is
$$R^{\circ*}=\bigcup_{n\in\mathbb{N}} R^{\circ n}$$
Consider $R:[n]\mapsto[n]$
In this case $R^{\circ*}=\bigcup_{m\in[n]}R^{\circ m}$

Given $M\in Mat_{IB}(m,n)$
Define $M^*\in Mat_{IB}(m,n)$
$M^*=M_{n}$
$M_{0}=I^n$ (the identity matrix)
$M_{k+1}=I^n\oplus(M\otimes M_{k})$

This gives $M^*$ as the adjacency matrix of $R^{\circ*}$ when M is the adjacency matrix of R

#### Preorder
A preorder $(P,\sqsubseteq)$ consists of a set P and a relation $\sqsubseteq$ on P (i.e. $\sqsubseteq \in \mathcal{P}(P\times P)$) satisfying the following two axioms:
- Reflexivity $\forall x\in P.x\sqsubseteq x$
- Transitivity $\forall x,y,z \in P.(x\sqsubseteq y \land y\sqsubseteq z)\implies x \sqsubseteq z$

A partial order or poset is a preoder that is also antisymmetric
$\forall x,y\in P.(x\sqsubseteq y \land y \sqsubseteq x)\implies x=y$
