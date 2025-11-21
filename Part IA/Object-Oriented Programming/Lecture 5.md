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
