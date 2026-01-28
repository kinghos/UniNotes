### Functions
A relation $R:A\mapsto B$ is said to be functional when it relates an element of A to at most one element of B
$\forall a \in A. \forall b_{1},b_{2}\in B. a\ R\ b_{1}\land a\ R\ b_{2}\implies b_{1}=b_{2}$
A partial function $f:A\rightharpoonup B$ is a functional relation from A to B

Closure properties:
1. The identity relation is functional
2. If $f:A \rightharpoonup B$ and $g:B\rightharpoonup C$, the relational composite $g\circ f: A\mapsto C$ is functional
Proof:

For a function, we write $f(a)\downarrow$ to mean that f is defined at a, i.e. there exists some unique $b\in B$ such that $a\ f\  b$. When $f(a)\downarrow$ holds we may write $f(a)$ to mean the unique b such that $a\ f\ b$, i.e. the value of b.

The domain of definition of a partial function is 
$$\text{dom}(f)=\{ a\in A \mid f(a)\downarrow \}$$
##### Extensionality
$$\begin{align}
f,g: A\rightharpoonup B, f=g \iff \\
\forall a\in A. f(a)\downarrow\iff g(a)\downarrow\\ 
\text{and } \forall a\in A.f(a)\downarrow \implies f(a)=g(a)
\end{align}$$
in other words, the functions share a domain of definition, and all inputs have the same output.

##### Cardinality
For all finite sets $A,B$ we have $\#(A,\rightharpoonup B)=(\#B+1)^{\#A}$
This is because f(a) can either be a member of B, or not a member of B, hence there are $\#A$ many possibilities that can take one of $\#B + 1$ values.

#### Total functions
A total function has a domain of definition that coincides with its domain (source), i.e. $f(a)\downarrow$ for all $a \in A$. This is written $f:A\to B$ and is called a function or map.

A relation is a function iff 
$$\begin{align}
\forall a \in A.\exists !b\in B.a\ R\ b
\end{align}$$
Total functions are closed under identity and composition, in the same way as partial functions.

#### Inductive definitions
For the naturals considering only the knowledge of +1, addition can be defined as such
$$\begin{align}
\text{add}:& \mathbb{N^2\to N}\\ 
\text{add}(m,0)&=m \\
\text{add}(m,n+1)&=\text{add}(m,n)+1
\end{align}$$
This is defined inductively.
##### Formal definition
Let A be a set, let $a_{0}\in A$ and fix $f:\mathbb{N}\times A\to A$. The function inductively defined from a and f is defined to be the unique function $\rho_{a,f}:\mathbb{N}\to A$, which is defined inductively from a to f.
$$\begin{align}
\rho_{a,f}(0)&=a_{0} \\
\rho(n+1)&=f(n,\rho_{a,f}(n))
\end{align}$$
In other words, this is defining a base case and an inductive case, and given both of these a function can be defined inductively

A relation $R:\mathbb{N}\mapsto A$ is $(a,f)$-closed whenever we have both $0\ R\ a$ and $n\ R\ x\implies(n+1)\ R\ f(n,x)$ for all $n\in \mathbb{N}$ and $x\in A$

##### Proof of existence of inductively defined functions
Given an element $a \in A$ and a function $f: \mathbb{N} \to A$, now let $\rho_{a,f}: \mathbb{N}\mapsto A$ be the intersection of all the $(a,f)$-closed relations $R:\mathbb{N}\mapsto A$
1. The relation $\rho_{a,f}: \mathbb{N}\mapsto A$ is functional and total, and therefore a function
2. The function $\rho_{a,f}:\mathbb{N}\to A$ is the unique $(a,f)$-closed function, i.e. it is the unique function satisfying both $\rho_{a,f}(0)=a$ and $\forall n\in \mathbb{N}.\rho_{a,f}(n+1)=f(n,\rho_{a,f}n)$
