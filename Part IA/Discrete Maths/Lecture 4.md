#### Disjunctions
$P \text{ or }Q$, $P\lor Q$
Either $P$, or $Q$, or both hold
To prove a goal of disjunctive form:
- Try to prove $P$ - if you succeed, that is enough
- Try to prove $Q$ - if you succeed, that is enough
- Break your proof into cases, proving in each case either $P$ or $Q$
To use an assumption of disjunctive form:
 - Assume P to establish the goal, and
 - Assume Q to establish the goal

##### Example
$$\text{Prove }Q \text{ using }P_{1}\lor P_{2}$$
We prove the following two cases in turn: (i) that assuming $P_1$, we have $Q$, and (ii) that assuming $P_2$ we have $Q$. Case (i): Assume $P_1$ *then prove Q using this and other assumptions*. Case (ii) *then prove Q using this and other assumptions*.

#### Lemmas and binomial theorem
$p\mid(a.b)\implies(p\mid a\lor p\mid b)$
For $a\equiv b (\mod m), x\equiv y(\mod m)$:
$a+x \equiv b+y (\mod m)$
$ia\equiv ib (\mod m)$

For all natural numbers m, n and primes p:
$(m+n)^p=m^p+n^p (\mod p)$
Hence,
$(m+1)^p =m^p+1(\mod p)$
And by induction:
$(m+i)^p=m^p+i(\mod p)$

#### Fermat's Little Theorem
For all natural numbers $i$ and primes $p$
1. $i^p=i(\mod p)$
2. $i^{p-1}=1(\mod p)$ whenever $i$ is not a multiple of $p$