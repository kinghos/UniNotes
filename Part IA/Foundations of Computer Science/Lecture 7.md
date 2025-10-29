Using option types forces you to check the option every time it is used, using pattern matching. This ensures you cover the error case
#### Dictionaries
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
