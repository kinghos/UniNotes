#### Ordered parings
$(a,b)$ or $\langle a,b\rangle$
$$(a,b)=(x,y)\implies a=x\land b=y$$
#### Products
The product $A\times B$ of two sets $A$ and $B$ is the set
$$A\times B=\{ x\mid \exists a \in A, b \in B.x=(a,b) \}$$
where $\forall a_{1},a_{2}\in A, b_{1},b_{2}\in B.$
$$(a_{1},b_{1})=(a_{2},b_{2})\iff(a_{1}=a_{2}\land b_{1}=b_{2})$$

The subset of ordered pairs from a set A with equal components is formally
$$\{ x\in A\times A \mid \exists a_{1} \in A. \exists a_{2}\in A.x=(a_{1},a_{2})\land a_{1}=a_{2}\}$$
but is often abbreviated with pattern-matching notation as
$$\{ (a_{1},a_{2})\in A\times A\mid a_{1}=a_{2} \}$$

#### Big union
For the family of sets
$$\mathcal{T}=\{ T\subseteq[5] \mid \text{sum of elements of T }\leq 2 \}$$
The big union of the family $\mathcal{T}$ is the set $\bigcup\mathcal{T}$ given by the union of the sets in $\mathcal{T}$:
$$n\in\bigcup\mathcal{T}\iff \exists T\in\mathcal{T}.n\in T$$
Hence $\bigcup\mathcal{T}=\{ 0,1,2 \}$

#### Big intersection
For the family of sets
$$\mathcal{S}=\{ S \subseteq [5] \mid \text{Sum of elements is }6\}$$
The big intersection of $\mathcal{S}$ is the set $\bigcap\mathcal{S}$ given by the intersections of the sets in $\mathcal{S}$:
$$n\in\bigcap\mathcal{S}\iff\forall S\in \mathcal{S}.n\in S$$
Hence, $\bigcap\mathcal{S}=\{ 2 \}$
