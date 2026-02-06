#### Images
Let $f:A\to B$ be a function
For any $b\in B$, the preimage or inverse image of b under f is the subset
$$f^*(b)=\{ a\in A\mid f(a)=b \}$$
Given $u \in B$, $f^*(u)=\{ a \in A \mid f(a) \in u \}$
Conversely, let $u \in A$. The direct/forward image or image of $u$ in $f$ is the subset
$$\begin{align}
f_{*}(u)&\subseteq B  \\
f_{*}(u)&=\{b\in B \mid \exists a \in u.f(a)=b  \}
\end{align}$$
Special case $u=A$.
$f_{*}(A)=\{ b\in B\mid \exists a\in A.f(a)=b \}$ = $\text{Range}(f)$
A function $f:A\to B$ also restricts to a function onto its image. In particular, we have
$$
\begin{align}
e_{f}&:A\to \text{Im}(f) \\
e_{f}(x)&=f(x)
\end{align}$$
$e_f$ is a surjection.

The coimage of $f:A\to B$ is the quotient $A\twoheadrightarrow A/\tilde{\ }_{f}$

#### Diagonalisation and Cantor's theorem
There exists no surjection from $A$ to $\mathcal{P}(A)$

#### Well-foundedness
Let $\prec:A\nrightarrow A$ be a relation on a set A 
1. An element $m \in S \subseteq A$ is a $≺$-minimal element of $S$ when $¬(\exists x \in S. x ≺ m)$
2. The binary relation $≺$ on A is called well-founded whenever each non-empty subset of A has a minimal element.
e.g. the strictly less than relation on the naturals is well-founded as there is a smallest natural number, but the strictly less than operator on the integers is not well-founded as there is no smallest integer.

A relation is well-founded iff there are no infinite descending chains.

#### The principle of well-founded induction
Let $\prec: A\nrightarrow A$ be well founded. Fix $S \subseteq A$
Then $S=A$ iff
$$\forall x\in A.(\forall y \prec x.y \in S)\implies x\in S$$
