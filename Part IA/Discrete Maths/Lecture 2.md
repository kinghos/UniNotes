#### Divisibility and Congruence
Let d and n be integers. We say that d divides n, and write $d\ |\ n$, whenever there is an integer k such that $n=kd$
e.g. $2\ |\ 4$ is true and $4\ |\ 2$ is not.

Fix a positive integer m. For integers a and b, we say that a is congruent to b modulo m, and write $a\equiv b (\mod m)$, whenever $m | (a-b)$
e.g. $18\equiv 2(\mod 4)$
$2\equiv-2(\mod4)$

##### Proposition
For every integer n,
1. n is even if and only if $n\equiv0(\mod2)$
2. n is odd if and only iff $n\equiv1(\mod2)$

Proof:
Let n be an integer.
Assume n is even.
RTP: $n\equiv0(\mod2)$, that is, $n-0=2i$ for an integer i.

#### Universal quantification
Universal statements are of the form
$\text{For all individuals x of the universe of discourse, the property} P(x)\text{ holds.}$
Or in symbols: $\forall x.P(x)$
The main proof strategy for proving universal statements is to let x stand for an arbitrary individual and prove P(x).
Make sure to use an **unused variable**. If x is used in the question, either declare x as fresh or use a different variable.

Universal instantiation - using an assumption of the form $\forall x.P(x)$, you can plug in any value, e.g. a, for x to conclude that $P(a)$ is true and so further assume it.

Fix a positive integer m. For integers a and b we have that $a\equiv b(\mod m)$ if and only if, for all positive integers n we have that $n\cdot a\equiv n \cdot b(\mod n \cdot m)$
Let m be a positive integer, and a and b be arbitrary integers.
RTP: $a\equiv b(\mod m)\iff(\forall \text{pos int n }n\cdot a=n \cdot b(\mod n \cdot m))$
Assume $a=b(\mod m)$ that in $a-b=m.i$ for an integer i.


#### Equality axioms
Every individual is equal to itself
$\forall x.x=x$
For any pair of equal individuals, if a property holds for one of them it also holds for the other one
$\forall x.\forall y.x=y\implies(P(x)\implies P(y))$

