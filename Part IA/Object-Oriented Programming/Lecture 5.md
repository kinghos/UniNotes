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

Java has functionality for default methods in interfaces. This came about because of a need to expand the language without breaking backwards compatibility. By adding default methods in interfaces, the classes that implement it will not break as they can simply use the default method.

Resolution rules:
- Classes always win
- Otherwise subinterfaces win. The method with the same signature in the most specific interface is selected
- If the choice is still ambiguous the class inheriting must override the method and be explicit

Diamond problem - it is unclear how many copies of the parent should be shared in multiple inheritance (such as when calling `super()`)

### Principles of OOP
#### Open-closed principle
Make your classes open to extension but closed to modification, i.e. make it easy to add new behaviour but hard to change existing behaviour
#### Liskov substitution principle
- Subtypes must be behaviourally substitutable for their base types without negative side effects
- In other words, replacing a base interface with an implemented class should not cause problems