#### Sections and retractions
Given $s:B\to A$ and $r:A\to B$,
$(s,r)$ form a section-retraction pair
when $r\circ s=\text{id}_{B}$ 
s is referred to as a section, and r as a retraction.
B is a retract of A

A function $f:A\to A$ is called idempotent when we have $f\circ f=f$
Every section retraction pair determines an idempotent. If $s$ is a section of $r$ the composite $s\circ r:A\to A$ is idempotent.

#### Bijections
A function $f:A\to B$ is said to be a bijection or isomorphism when there exists a function $g:B\to A$ that is both a retraction and a section of $f$ in the sense that $g\circ f=\text{id}_{A}$ and $f\circ g=\text{id}_{B}$
$f^{-1}:A\to B$ is the inverse to a bijection $f:A\to B$

$$\begin{equation}
\#\text{Bij}(A,B)=
\begin{cases}
0 & \text{if }\#A\not=\#B \\
n! & \text{if } \#A=\#B = n
\end{cases}
\end{equation}$$
Bijections/isomorphisms are closed under identity and composition

#### Equivalence relations
A relation $E:A\mapsto A$ is called an equivalence relation when it is reflexive, transitive, and symmetric.
$\text{EqRel}(A)$ is the set of all equivalence relations on A

The equivalence class of a given element $a\in A$ in $E$ is the subset $[a]_{E}\subseteq A$ spanned by elements related to a in $E$, i.e. $[a]_{E}=\{ x\in A\mid x\ E\ a \}$

#### Set partition
A partition of a set of $A$ is a set $P\in\mathcal{P}(A)$ of non empty subsets of $A$ whose elements are referred to as blocks, satisfying the following conditions:
1. the union of all blocks is all of A, $\bigcup P=A;$
2. the blocks are pairwise disjoint, i.e. for all $b_{1}\not=b_{2}\in P$ we have $b_{1}\cap b_{2}=\emptyset$
We write $\text{Part}(A)$ for the set of partitions of A

For every set A we can define a bijection $\Phi:\text{EqRel}(A)\to\text{Part}(A)$ sending every equivalence relation $E$ on $A$ to the partition $\Phi(E)=\{ [a]_{E}\mid a \in A \}$ whose blocks consist of the equivalence classes of each element of A.
