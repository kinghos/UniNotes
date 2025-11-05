#### Breadth First Search
```ocaml
let rec nbreadth = function
| [] -> []
| Lf :: ts -> nbreadth ts
| Br (v, t, u) :: ts ->
    v :: nbreadth (ts @ [t; u])
```
`ts @ [ t; u ]` is a queue.
This is very inefficient, as there are an enormous queue of nodes to search and there is a wasteful use of append. It takes 25 seconds to search a depth 12 binary tree of 4095 labels

### Efficient Functional Queues
- Represent the queue $x_1\; x_2\; \ldots\; x_m\; y_n\; \ldots\; y_1$ by any pair of lists
$$ ([x_1,x_2,\ldots,x_m], \; [y_1,y_2,\ldots,y_n])$$
- Remove items from the front list, if empty move rear to front, reversed
- Average time per operation is $O(1)$
##### Example
`[1; 2; 3; 4; 5; 6]` -> `[2; 3; 4; 5; 6; 7]`
Functional queue: `([1; 2; 3], [6; 5; 4])`
Dequeue by pattern matching and discarding the first list: `[1; 2; 3] = 1::[2; 3]`
Enqueue by consing 7 to the second list: `7:: [6; 5; 4]` -> `[7; 6; 5; 4]`

```ocaml
type 'a queue =
| Q of 'a list * 'a list

let norm = function
| Q ([], tls) -> Q (List.rev tls, [])
| q -> q

let qnull = function
| Q ([], []) -> true
| _ -> false

let enq (Q (hds, tls)) x = norm (Q (hds, x::tls))

exception Empty
let deq = function
| Q (x::hds, tls) -> norm (Q (hds, tls))
| _ -> raise Empty

let qempty = Q ([], [])

let qhd = function
| Q (x::_, _) -> x
| _ -> raise Empty
```
`norm` here ensures that the front part is never empty unless the entire queue is empty.

#### Breadth First Search with Queues
```ocaml
let rec breadth q =
  if qnull q then []
  else
    match qhd q with
    | Lf -> breadth (deq q)
    | Br (v, t, u) -> v :: breadth (enq (enq (deq q) t) u)
```
Massive speedup compared to the other algorithm.

### Iterative deepening
Breadth-first search is not practical for infinite trees, as it uses too much space. Breadth-first examines $O(b^d)$ nodes, and since they are all stored, this means the space complexity is the same. Depth-first iterative deepening performs repeated depth-first searches, each time discarding the results of the previous search. Thus the space complexity becomes $O(d)$.

#### Stacks
Often treated as an imperative data structure - push and pop change an existing stack, not returning a new one.