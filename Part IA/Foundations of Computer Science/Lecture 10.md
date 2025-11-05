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