### Sorting
The number of comparisons is usually the measure of efficiency for a sorting algorithm.

#### Insertion sort
```ocaml
let rec ins x = function
  | [] -> [x]
  | y::ys -> if x <= y then x :: y :: ys
			 else y :: ins x ys

let rec insort = function
  | [] -> []
  | x::xs -> ins x (insort xs)
```
