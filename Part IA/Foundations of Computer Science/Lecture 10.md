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