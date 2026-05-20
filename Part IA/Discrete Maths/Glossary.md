[[DiscMathSummaryNotes.pdf]]

| Term              | Definition                                                                                          |
| ----------------- | --------------------------------------------------------------------------------------------------- |
| [[Modus Ponens]]  | If $P$ and $P\implies Q$ then $Q$                                                                   |
| Rational number   | For a rational number $r$, $r=\frac{a}{b}$ where $a$ is an integer and $b$ is a **nonzero** integer |
| Natural number    | Integers of the set $\{ 0,1,2,\dots \}$                                                             |
| Monoid            | A set with a binary operator and neutral element                                                    |
| Family            | A set of subsets $\mathcal{F(P(P(U)))}$                                                             |
| Injection         | one-to-one: $\forall x_{1},x_{2}\in X.f(x_{1})=f(x_{2})\implies x_{1}=x_{2}$                        |
| Surjection        | onto: $\forall b \in B.\exists a\in A.f(a)=b$                                                       |
| Bézout's identity | $\exists x,y\in \mathbb{Z}.ax+by=gcd(a,b)$                                                          |
|                   |                                                                                                     |

A set is countable if a surjection exists to that set

#### Subset Construction
- Table of states to characters in the alphabet
- Start at the start of the NFA and consider the states which are reached immediately (this includes ones connected by $\epsilon$ from the start state)
- Consider what the inputs will do, write the set of outputs on the respective cell
- Repeat in lexicographic order for all sets of states reachable 