### Expression evaluation
Focus on expressions, ignoring side effects 

```ocaml
let rec power x n = 
  if n = 1 then x
  else if even n then
    power (x *. x) (n / 2)
  else 
    x *= power (x *. x) (n / 2)
```
`val power : float -> int -> float`

### Summing
#### Simple recursive summing
```ocaml
let rec nsum n =
  if n = 0 then
    0
  else
    n + nsum (n - 1)
```
In this example, nothing can progress until the final expression is evaluated - `nsum(0)`. This means all intermediate values are stored in the stack, which takes up memory, and if enough layers are reached there can be a stack overflow error.
$$
\begin{aligned}
\text{nsum}\;3 \Rightarrow &\; 3 + (\text{nsum}\;2) \\
               \Rightarrow &\; 3 + (2 + (\text{nsum}\;1)) \\
               \Rightarrow &\; 3 + (2 + (1 + (\text{nsum}\;0))) \\
               \Rightarrow &\; 3 + (2 + (1 + 0))
\end{aligned}
$$
#### Iteratively summing and tail recursive algorithms
```ocaml
let rec summing n total =
  if n = 0 then
    total
  else
    summing (n - 1) (n + total)
    ```
The argument "total" here acts as an accumulator to keep track of the total without using the stack. This is an *iterative* or *tail recursive* algorithm.
What makes this algorithm tail recursive is that the last thing it does is call itself - in the first example, the function adds `n` after calling itself, hence it is not tail recursive.

Tail recursion is only efficient if the compiler can detect it. It mainly saves space but can also speed up a program. It should only be used when the gain is significant.

#### Multiple function calls
When recursively calling a function, consider any side effects from calling the function more than once. If the same recursive call is used more than once, a local variable can be used to store the output.
```ocaml
let x = 2.0 in
let y = Float.pow x 20.0 in
y *. (x /. y)
```

### Complexity
#### Asymptotic complexity
Asymptotic complexity refers to how costs grow with increasing inputs. Space complexity can never exceed time complexity, so time complexity often greatly exceeds space complexity.

$$
\begin{aligned}
 O(2g(n)) & \text{ is the same as } O(g(n)) \\
 O(\log_{10}n) & \text{ is the same as } O(\ln n)  \\
 O(n^2+50n+36) & \text{ is the same as } O(n^2) \\[1.5ex]
 O(n^2) & \text{ is contained in }  O(n^3) \\
 O(2^n) & \text{ is contained in }  O(3^n)  \\
 O(\log n) & \text{ is contained in } O(\sqrt n)
\end{aligned}
$$
#### Analysing complexity of functions
```ocaml
let rec nsum n =
  if n = 0 then
    0
  else
    n + nsum (n - 1)
```
Given n+1, the function doe a constant amount of work, then calls itself with n.
This gives the recurrence equations $T(0)=1$ and $T(n+1)=T(n)+1$. Hence, the cost is linear.

```ocaml
let rec nsumsum n =
  if n = 0 then
    0
  else
    nsum n + nsumsum (n - 1)
```
This function call nsum which we know takes $O(n)$, and then calls itself once,
hence giving the recurrence relations $T(0)=1$ and $T(n+1)=T(n)+n$. Hence, the cost is $O(n^2)$
