---
tags:
  - booleanAlgebra
---

| Gate | Symbol         |
| ---- | -------------- |
| NOT  | $\overline{A}$ |
| AND  | $A.B$          |
| OR   | $A+B$          |
| XOR  | $A\oplus B$    |
##### Order of operations
AND takes precedence over OR, e.g.
$a.b+c.d = (a.b)+(c.d)$

##### Distribution
$a.(b+c+\dots)=(a.b)+(a.c)+\dots$
$a+(b.c. \dots)=(a+b).(a+c). \dots$
##### Absorption
$a+(a.c)=a$
$a.(a+c)=a$

##### Consensus theorem
$a.b +\bar{a}.c + b.c =a.b +\bar{a}.c$
$(a+b).(\bar{a}+c).(b+c)=(a+b).(\bar{a}+c)$

Try expanding each term until it includes one instance of each variable, then simplify.
e.g. $a.b+a = a.b + a.b + a.\bar{b} = a.\bar{b}+a.b=a$

##### DeMorgan's Theorem
$\overline{a+b+c+\dots}=\bar{a}.\bar{b}.\bar{c}$
$\overline{a.b.c.\dots}={\bar{a}+\bar{b}+\bar{c}}$

##### Truth tables
A minterm must contain all variables (in either complement or uncomplemented form). e.g. $\bar{x}.y.z$ but not $y.z$. Minterms are essentially the values for which the function outputs 1.

##### Disjunctive Normal Form
- A boolean function expressed as the disjunction (ORing) of its minterms is said to be in the Disjunctive Normal Form
- A boolean function expressed as the ORing of ANDed variables is said to be in Sum of Products form


A maxterm of n boolean variables is the disjunction (ORing) of all the variables either in complemented or uncomplemented form.
$$
f = x.\bar{y}.z+x.\bar{y}.z+x.y.\bar{z}
$$

These forms can be found with [[Karnaugh Maps]] or [[Quine-McCluskey Minimisation]]

