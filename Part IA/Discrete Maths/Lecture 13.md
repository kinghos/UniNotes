### Relations
A relation $R:A\mapsto B$ or "relation R from A to B" is a subset of $R\subseteq A\times B$.
i.e. a set of pairs (a,b) where $a\in A, b\in B$
Alternatively $a\ R\ b$ means $(a,b)\in R$

$\emptyset: A\mapsto B$ is empty
$(A\times B):A\mapsto B$ is the full relation
$\text{Id}_{A}:A\mapsto A$ is the identity relation
#### Relational composition
$R:A\mapsto B$
$S:B\mapsto C$
$S\circ C: A\mapsto C$
$S\circ C \subseteq A\times C$

Relational composition is associative and unital

#### Relations and matrices
Given a semiring $(S,0,\oplus,1,\odot)$, an $(m\times n)$ matrix M over S is given by $M_{i,j}\in S$ for all $0\leq i<m,0\leq j<n$

A relation can be written as a Boolean matrix and vice versa
Matrix product is the same as relational composition for the boolean semiring