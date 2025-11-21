#### Modular arithmetic
For every positive integer m, the integers modulo m are 
$\mathbb{Z}_{m} : 0,1, \dots, m-1$
The operators $+_m$ and $\cdot_m$ work as follows
$k+_{m}l=\text{rem}(k+l,m)$,
$k\cdot_{m} l=rem(kl, m)$
For all $0\leq k, l<m$

For all natural numbers $m>1$, the modular arithmetic structure
$$(\mathbb{Z}_{m},0,+_{m},1,\cdot_{m})$$
is a commutative ring

#### Linear combinations
An integer r is said to be a linear combination of a pair of integers m and n whenever there are integers s and t such that $s\cdot m + t\cdot n=r$
$x$ has a reciprocal in $\mathbb{Z}_m\iff$ 1 is an integer linear combination of $m$ and $x$ 

#### Sets
- $\in$ is known as the set membership predicate.
- Set comprehension is defining a set by means of a property that precisely characterises all the elements of the set.
- Two sets are equal when they have the same elements.
- Hence, equivalent predicates specify equal sets

#### Greatest common divisor
The set of divisors is defined as
$D(n)=\{d\in\mathbb{N}:d\mid n\}$
The common divisors of pairs of natural numbers is defined as 
$CD(m,n)=\{d\in\mathbb{N}:d\mid m\land d\mid n\}$

#### Euclid's Algorithm
Let $m$ and $m'$ be natural numbers and let $n$ be a positive integer such that $m\equiv m' \pmod n$. Then, $$
CD(m,n)=CD(m',n)
$$
For all positive integers m and n, $CD(m,n)=D(n)$ if $n\mid m$, otherwise $=CD(n, \text{rem}(m,n))$
Since n is the greatest divisor in $D(n)$, the greatest common divisor can be found through a recursive procedure:
$$
\begin{equation}
  gcd(m,n)=\begin{cases}
    n & \text{if $n\mid m$}\\
    gcd(n,\text{rem}(m,n)) & \text{otherwise}.
  \end{cases}
\end{equation}
$$
This is Euclid's algorithm.