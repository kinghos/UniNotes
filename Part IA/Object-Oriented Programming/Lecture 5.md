### Polymorphism
Many kinds of objects can provide the same method, and the method can be invoked knowing which kind of object will perform it
#### Static polymorphism
- Decide at compile-time
- Since the true type of the object is unknown, just run the parent method
- Type errors give compile errors
#### Dynamic polymorphism
- Run the method in the child
- Must be done at runtime since that is when we know the child's type
- Type errors cause run-time faults
All methods in Java are dynamic polymorphic.

#### Multiple inheritance
**Java does not support this**
Multiple inheritance of behaviour:
- Name clashes
- Which method from each function should be inherited with a shared name?
Multiple inheritance of state:
- Name clashes - need to specify which state is being referred to
- Less readable and more likely to have bugs
Can still be useful - but risky

Java does not allow classes to have multiple parents, but multiple interfaces can be implemented. This means there cannot be name clashes