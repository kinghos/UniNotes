### Formal Languages
#### Alphabets
An alphabet is specified by giving a finite set $\Sigma$ whose elements are called symbols. Any finite set can serve as an alphabet.
A string over $\Sigma$ is a finite list of symbols in $\Sigma$. $\Sigma^*$ is the set of all strings, and for a string $u \in \Sigma^*$ we write $|u|$ for its length.

The concatenation of two strings $u,v$ is denoted $uv$ and is obtained by joining them end to end. It is unital and associative.

#### Formal languages
A formal language over an alphabet $\Sigma$ is defined to be a subset of $\Sigma^*$, i.e. a set of strings over $\Sigma$.

##### Inductive definition
$$\frac{\quad}{\quad0\quad}\quad \frac{\quad x\quad }{\quad x+1\quad}$$
This notation denotes $\mathbb{N}$. A rule that has no premise (top part) is an axiom. The bottom part is known as the conclusion

$$\frac{{\quad u\quad v \quad w\quad}}{\quad x \quad}$$
This means "if $u,v,w\in S$, then $x\in S$"
Given a set $\mathcal{R}$ of rules, we write
$$\begin{align}
\text{Cl}_{R}\subseteq \mathcal{P}(\Sigma^*)  \\
\end{align}$$
$\text{Cl}_{R}=$ intersection of all closure conditions indicated by the rules in $\mathcal{R}$
