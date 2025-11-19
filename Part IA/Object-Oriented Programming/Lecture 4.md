Pass by value is all that Java offers. However, objects can be changed since they are stored as references in variables. **This is still pass-by-value.**

### Inheritance
Subclasses inherit from superclasses/base classes using the `extends` keyword.
- Type is inherited
- All attributes and behaviours are inherited
- Direct access to public and protected members of that class (but not private unless there exist methods to access them)
- Subclasses can redefines some inherited behaviour, or add new attributes and behaviour
