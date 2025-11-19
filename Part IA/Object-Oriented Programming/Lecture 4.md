Pass by value is all that Java offers. However, objects can be changed since they are stored as references in variables. **This is still pass-by-value.**

### Inheritance
Subclasses inherit from superclasses/base classes using the `extends` keyword.
- Type is inherited
- All attributes and behaviours are inherited
- Direct access to public and protected members of that class (but not private unless there exist methods to access them)
- Subclasses can redefines some inherited behaviour, or add new attributes and behaviour
The `super()` function should be used to call the constructor of a parent class and provide arguments.

#### Casting
Widening cast - moving up the tree with implicit type casting, e.g. calling a function made for a Person on a Student
Narrowing cast - moving down the tree. Can be problematic, as there is not enough info to represent the "specialised" class. Casting to the correct class can fix this.
#### Shadowing
`super.x` can be used to access a parent attribute (if another attribute in the subclass has the same name). Alternatively, if the parent is called B, `((B)this).x`

#### Overriding
Use `@Override` for code clarity

#### Abstract classes and methods
- Sometimes we want to force a subclass to implement a method but there isn't a convenient default behaviour to put in the parent
- An abstract method is used in a base class to do this
- It has no implementation whatsoever
Italics indicate the class or method is abstract on a UML diagram.

#### Interfaces
An interface is a contract that groups together required methods
- It is a collection of exclusively abstract functions that force classes that inherit from them to provide concrete implementations
- Interfaces are declared using `interface`
- They are used via `implements`
![[InterfacesVsClasses.png]]