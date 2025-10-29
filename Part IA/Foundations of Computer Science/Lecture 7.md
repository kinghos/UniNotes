Using option types forces you to check the option every time it is used, using pattern matching. This ensures you cover the error case
### Dictionaries
A dictionary attaches values to identifiers. It has the operations:
- lookup
- update/insert
- delete
- empty
- missing - exception for errors in lookup and delete
The simplest representation for a dictionary is an association list (list of key/value tuples)

```ocaml
exception Missing

let rec lookup = function
  | [], a -> raise Missing
  | (x, y) :: pairs, a ->
    if x=a then
      y
    else
      lookup (pairs, a)
      
let update (l, b, y) = (b, y) :: l
```

### Binary Search Trees
The time complexity for lookup is only $O(\log n)$ when the tree is balanced.
```ocaml
let rec lookup b = function
| Br ((a, x), t1, t2) ->
    if b < a then
      lookup b t1
    else if a < b then
      lookup b t2
    else
      x
| Lf -> raise (Missing b)
```

```ocaml
let rec update k v = function
| Lf -> Br ((k, v), Lf, Lf)
| Br ((a, x), t1, t2) ->
    if k < a then
      Br ((a, x), update k v t1, t2)
    else if a < k then
      Br ((a, x), t1, update k v t2)
    else (* a = k *)
      Br ((a, v), t1, t2)
```
This code reconstructs a new tree in which the target value is replaced.

#### Tree Traversal
- Preorder - label first
- Inorder - label midway
- Postorder - label last
```ocaml
let rec preorder = function
| Lf -> []
| Br (v, t1, t2) ->
    [v] @ preorder t1 @ preorder t2

let rec inorder = function
| Lf -> []
| Br (v, t1, t2) ->
    inorder t1 @ [v] @ inorder t2
    
let rec postorder = function
| Lf -> []
| Br (v, t1, t2) ->
    postorder t1 @ postorder t2 @ [v]
```
For binary search trees, inorder gives a sorted list from the tree, by "squashing down" the tree.

#### Functional arrays
- Immutable
- $O(\log n)$ access time (slower than a conventional array which is $O(1)$)

Lookup function
```ocaml
exception Subscript
let rec sub = function
| Lf, _ -> raise Subscript  (* Not found *)
| Br (v, t1, t2), k ->
    if k = 1 then v
    else if k mod 2 = 0 then
      sub (t1, k / 2)
    else
      sub (t2, k / 2)
```
Alternatively:
```ocaml
let rec sub = function (* Alternative implementation *)
| Lf, _ -> raise Subscript
| Br (v, t1, t2), 1 -> v
| Br (v, t1, t2), k when k mod 2 = 0 -> sub (t1, k / 2)
| Br (v, t1, t2), k -> sub (t2, k / 2)
```
