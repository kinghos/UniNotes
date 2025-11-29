 Euclid's algorithm relies on two properties:
- both $\text{gcd}(m,n)\mid m$ and $\text{gcd}(m,n)\mid n$, and
- for all positive integers $d$ such that $d\mid m$ and $d\mid n$ it necessarily follows that $d \mid \text{gcd}(m,n)$
#### Properties
- Commutative
- Associative
- Linearity - $\text{gcd}(l\cdot m, l\cdot n)=l\cdot \text{gcd}(m, n)$

- Two natural numbers are said to be coprime whenever their greatest common divisor is 1
#### Euclid's Theorem
For positive integers k, m and if k | mn and gcd(k,m) = 1 then k| n
in other words, if a number divides the product of two numbers, it must divide at least one of them.

- For prime $p$, every non-zero element $i$ of $\mathbb{Z}_p$ has $[i^{p-2}]_{p}$ as multiplicative inverse. Hence $\mathbb{Z}_p$ is referred to as a field.
- An integer $r$ is said to be a linear combination of a pair of integers $m$ and $n$ whenever there exist a pair of integers $s$ and $t$, referred to as  the coefficients of the linear combination such that 
$$\begin{bmatrix}
s&t
\end{bmatrix}\cdot \begin{bmatrix}
m \\n
\end{bmatrix}=r$$
that is $s\cdot m+t\cdot n=r$

For all positive integers $m$ and $n$,
1. $\text{gcd}(m,n)$ is a linear combination of m and n and
2. a pair $\text{lc}_1(m_,n),\text{lc}_{1}(m,n)$ of integer coefficients for it, such that
$$\begin{bmatrix}
\text{lc}_1(m_,n)&\text{lc}_{1}(m,n)
\end{bmatrix}\cdot \begin{bmatrix}
m \\ n
\end{bmatrix} = \text{gcd}(m,n) $$
can be efficiently computed.

This extends Euclid's algorithm from computing on pairs of positive integers to computing on pairs of triples $((s,t),r)$ with $s,t$ integers and $r$ a positive integer satisfying the invariant that $s,t$ are coefficients expressing $r$ as an integer linear combination of $m$ and $n$.
