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
