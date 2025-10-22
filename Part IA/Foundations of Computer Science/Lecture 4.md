Use of `function` and `match ... with ...` is interchangeable.

#### Linear Search
$O(n)$ complexity, ordered searching would be better at $O(\log n)$ and indexed searching best at $O(1)$. 
##### Equality test
Equality testing using `=` is fine for integers, bools, floats e.g. but not for functions.
###### List membership
```ocaml
let rec member x = function
  | [] -> false
  | y::l -> x = y || member x l
```
###### Intersection
```ocaml
let rec inter xs ys =
  match xs, ys with
  | [], ys -> []
  | x::xs, ys ->
    if member x ys then
      x :: inter x ys
    else
      inter xs ys
```