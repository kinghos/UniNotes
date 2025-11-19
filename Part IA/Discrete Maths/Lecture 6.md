#### Semirings
A semiring is an algebraic structure with 
- a commutative monoid structure, say $(0,\oplus)$
- a monoid structure, say $(1, \otimes)$
satisfying the distributivity laws.
A semiring is commutative whenever $\otimes$ is

#### Cancellation
A binary operation $\bullet$ allows cancellation by an element c
- on the left: if $c\bullet x = c \bullet y$ implies $x=y$
- on the right: if $x \bullet c=y\bullet c$ implies $x=y$
#### Inverses
For a monoid with a neutral element e and a binary operation $\bullet$, and element x is said to admit an
- inverse on the left if there exists an element $\ell$ such that $\ell \bullet x = e$
- inverse on the right if there exists an element r such that $x\bullet r = e$
- inverse if it admits both left and right inverses
#### Groups
A group is a monoid in which every element has an inverse. An Abelian group is a group for which the monoid is commutative

A number x is said to admit an additive inverse whenever there exists a number y such that $x+y=0$
A number x is said to admit a multiplicative inverse whenever there exists a number y such that $x\cdot y=1$
#### Rings
A ring is a semiring $(0,\oplus,1,\otimes)$ in which the commutative monoid $(0,\oplus)$ is a group
A ring is commutative if so is the monoid $(1,\otimes)$
#### Division Theorem
For every natural number m and positive natural number n, there exists a unique pair of integers q and r such that $q\geq 0, 0\leq r\leq n$ and $m=q\cdot n+r$
This is denoted as $\text{quo}(m,n)$ and $\text{rem}(m,n)$
