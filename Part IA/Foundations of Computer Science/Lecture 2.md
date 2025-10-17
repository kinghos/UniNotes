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
When recursively calling a function, consider any side effects from calling the function more than once. If the same 