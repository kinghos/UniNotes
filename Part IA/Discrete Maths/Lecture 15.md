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
Let A be a set, and fix $a\in A$ and $f:\mathbb{N}\times A\to A$. The function inductively defined from a and f is defined to be the unique function $\rho_{a,f}:\mathbb{N}\to A$, which is defined inductively from a to f.
$$\begin{align}
\rho_{a,f}(0)=a_{0} \\

\end{align}$$