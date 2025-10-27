### Custom Datatypes
An enumeration type can be declared like so:
```ocaml
type vehicle = Bike
             | Motorbike
             | Car
             | Lorry
```
The representation in memory is more efficient than if stored with strings. More vehicles can be added by extending the definitions. Different custom types cannot be intermixed, unlike strings or integers.

#### Generalising
```ocaml
type vehicle = Bike
    | Motorbike of int
    | Car of bool
    | Lorry of int

let v = Motorbike 250
```
This can then be pattern matched
```ocaml
let wheels = function
  | Bike -> 2
  | Motorbike _ -> 2
  | Car robin -> if robin then 3 else 4
  | Lorry w -> w
```
