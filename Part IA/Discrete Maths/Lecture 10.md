#### Euclid's infinitude of primes
Suppose by contradiction that there are finite prime numbers. Let $p_{1},p_{2},\dots,p_{n}$ be the prime numbers for $n\in\mathbb{N}$
Consider $(p_{1}\cdot p_{2}\cdot\dots \cdot p_{n})+1$ which is not prime. So there is $p_i$ such that $p_{1}\mid(p_{1}\dots p_{n})+1$. Also $p_{i}\mid(p_{i}\dots p_{n})$ and so $p_{i}\mid[(p_{1}\dots p_{n})+1]-(p_{1}\dots p_{n})=1$ which is a contradiction

### Sets
$\in$ is the membership predicate.
$x\not\in A$ for $\lnot(x\in A)$
##### Extensionality axiom
Two sets are equal if they have the same elements

#### Subsets and supersets
$A\subseteq B$, means A is a subset of B whenever $\forall x.x\in A\implies x\in B$
Also, B is a superset of A, $B\supseteq A$
$\subseteq$ means they can be equal, $\subset$ means they cannot be equal.

1. Reflexivity
	For all sets A, $A\subseteq A$
2. Transitivity
	For all sets A, B, C, $(A\subseteq B\land B\subseteq C)\implies A\subseteq C$
3. Antisymmetry
	For all sets A, B, $(A\subseteq B\land B\subseteq A)\implies A=B$

#### Separation principle
For any set $A$ and any definable property $P$, there is a set containing precisely those elements of $A$ for which the property $P$ holds.
$$\{ x\in A\mid P(x) \}$$
#### Russell's paradox
Definitions of sets $\{ x \mid P(x) \}$ should not be allowed (defining a set based on already constructed sets)
If $u=\{ x\mid \lnot(x\in x) \}$ is a set, then $u\in u\iff \lnot(u\in u)$

#### Empty set and cardinality
Denoted $\emptyset$ or $\{  \}$
The cardinality of a set specifies its size. If this is a natural number, then the set is said to be finite.
Typical notations for the cardinality of a set S are $\#S$ or $|S|$
e.g. $\#\emptyset=0$
For $n\in\mathbb{N}$,
$$[n]=\{ x\in\mathbb{N}\mid x <n \}$$
#### Powerset axiom
For any set, there is a set consisting of all its subsets, denoted $\mathcal{P(U)}$