#### Logical characterisation of isomorphisms
The following statements are equivalent for $f: A\to B$
1. the function $f: A\to B$ is invertible (an isomorphism)
2. we have $\forall B\in B.\exists!a\in A.f(a)=b$
3. we have both $\forall b\in b.\exists a\in A.f(a)=b$ and $\forall a_{1},a_{2} \in A.f(a_{1})=f(a_{2})\implies a_{1}=a_{2}$

The co-domain is the set the function maps to, whereas the range is the subset of the co-domain which contains all values that the domain of the function maps to.
#### Surjective functions
A function $f:A\to B$ is surjective when $\forall b\in B.\exists a\in A.f(a)=b$
Let A be a set. We have a function
$!A:A\to[1]$
$!A$ is surjective **iff A non-empty!!**
Denoted $f:A\twoheadrightarrow B$

Let E be an equivalence relation on a set A, and let $q:A\to A/E$ be the quotient function that sends $a\in A$ to its equivalence class $[a]_{E}$. Then $q:A\to A/E$ is surjective

The projection function $\pi_{1}:A\times  B\to A$ sending $(a,b)$ to $a$ is surjective if and only if either $B\not=\emptyset$ or $A=\emptyset$

The identity function is a surjection and the composition of surjections yields a surjection.

#### Enumerability
A set A is said to be enumerable whenever there exists a surjection $e:\mathbb{N}\twoheadrightarrow A$, referred to as an enumeration.
Can be thought of as a listing of the elements of A.

#### Countability
A set A is countable when it is enumerable or it is empty. All finite sets are countable.
Alternatively, A is countable iff $A+[1]$ is enumerable