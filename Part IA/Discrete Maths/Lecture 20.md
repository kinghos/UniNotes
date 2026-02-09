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

A derivation in $\mathcal{R}$ is a tree whose root is the conclusion of a rule, and the subnodes are the conclusions of other rules, and so on. Leaves are axioms.
A syntactic presentation of a formal language over $\Sigma$ is a set of rules $\mathcal{R}$ over $\Sigma^*$

$$\frac{}{\quad (x,y) \quad}((x,y) \in R)$$
This is called a side condition, as the rule only applies when $x\mathrel{R} y$

#### Rule Induction
Let $\mathcal{R}$ be a set of syntactic rules over a set $X$. Let $X_\mathcal{R}\subseteq X$ be the subset containing just those $x \in X$ such that there exists a derivation of $x$ in $\mathcal{R}$.
1. $X_\mathcal{R}$ is closed under every rule $\mathcal{R}$ i.e. $X_{\mathcal{R}}\in\text{Cl}_{\mathcal{R}}$
2. $X_\mathcal{R}$ is the smallest subset closed under every rule of $\mathcal{R}$ i.e. $X_{\mathcal{R}}=\cap \text{Cl}_{\mathcal{R}}$
Proof:
Fix a rule $\frac{{\quad u_{1}\dots}u_{n}\quad}{v}$. Given $u_{1}\dots u_{n}\in X_{\mathcal{R}}$, we need to verify $v\in X_{\mathcal{R}}$
Derivations need to be combined to obtain a derivation of $v$:
$$\frac{\frac{{\vdots}}{u_{1}}\quad\dots\quad \frac{{\vdots}}{u_{n}}}{v}$$
This shows $X_{\mathcal{R}}\in\text{Cl}_{\mathcal{R}}$
Now we want to prove statement 2. Fix $S \in \text{{Cl}}_{\mathcal{R}}$, and RTP $X_{\mathcal{R}} \in S$
i.e. for any derivation in $\mathcal{R}$, its root lies in $S$.
$$\forall n\in \mathbb{N}\text{, the root of any deriviation with height}\leq n  \text{ lies in }S$$

Inductive case: Suppose that the root of every derivation of height $\leq n$ lies in $S$. We want to prove the same for derivatives of height $\leq n+1$
Consider $$\frac{\frac{{\vdots}}{u_{1}}\quad\dots\quad \frac{{\vdots}}{u_{n}}}{v}$$
This must come from the following rule 
$$\frac{{\quad u_{1}\dots}u_{n}\quad}{v}$$
We need to show $v$ lies in $S$. All of the subderivations of $u_i$ depicted above have height less than or equal to $n$, therefore the inductive hypothesis ensures each $u_i \in S$.