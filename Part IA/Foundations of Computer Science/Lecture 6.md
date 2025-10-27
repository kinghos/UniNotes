#### Custom Datatypes
An enumeration type can be declared like so:
```ocaml
type vehicle = Bike
             | Motorbike
             | Car
             | Lorry
```
The representation in memory is more efficient than if stored with strings. More vehicles can be added by extending the definitions. Different custom types cannot be intermixed, un