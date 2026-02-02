A and B are isomorphic when there exists some iso $f:A\to B$
$f:A ≅B$   "f is an iso from A to B"
$A≅B$         "A and B are isomorphic"

$≅:\text{Set} \mapsto\text{Set}$ is an equivalence relation

A predicate on a set A is a function 
$$\begin{align}
\phi :A\to[2] \\
[2]=\{ 0,1 \}
\end{align}
$$
"$\phi$ holds of a" when $\phi(a)=1$

The indicator function of $S\subseteq A$ is the predicate
$$\begin{align}
\chi_{S}=A\to[2] \\
\chi_{S}(a)=\begin{cases}
1 & \text{if }a \in S \\
0 & \text{if }a \not \in S
\end{cases}
\end{align}$$
Given a predicate $\phi: A\to[2]$, define the comprehension of $\phi$ to be the following subset $[\phi]\subseteq A$ spanned by elements at which $[\phi]$ holds.
$$[\phi]=\{ a\in A\mid \phi(a)=1 \}$$
The mappings (indicator and comprehension respectively)
$$\begin{align} 
\chi_{(-)}:\mathcal{P}(A)\to(A\to[2]) \\
[-]:(A\to[2])\to\mathcal{P}(A)
\end{align}$$
given by indicator functions and comprehension are mutually inverse.
Thus, $\mathcal{P}(A)\cong(A\to[2])$

For any set $X$, we have $\mathcal{P}(X+[1])\cong\mathcal{P}(X)+\mathcal{P}(X)$, where $+$ denotes disjoint union.