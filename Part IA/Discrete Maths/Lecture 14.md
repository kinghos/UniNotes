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
This composition will produce lengths of increasing lengths, e.g. if $(A,R)$ has the path $x\to y\to z$ then $(A,R^{\circ2})$ will compose the edges and form a path of $x\to z$, i.e. it will form paths of length 2 i