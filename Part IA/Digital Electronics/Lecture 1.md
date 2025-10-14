### Logic Gates and Boolean Algebra

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
$a.b. +\bar{a}.c + b.c =a.b +\bar{a}.c$
$(a+b).(\bar{a}+c).(b+c)=(a+b).(\bar{a}+c)$

Try expanding each term until it includes one instance of each variable, then simplify.
e.g. $a.b+a = a.b + a.b + a.\bar{b} = a.\bar{b}+a.b=a$

##### DeMorgan's Theorem
$a+b+c+\dots=\overline{\bar{a}.\bar{b}.\bar{c}}$
$a.b.c.\dots=\overline{\bar{a}+\bar{b}+\bar{c}}$
