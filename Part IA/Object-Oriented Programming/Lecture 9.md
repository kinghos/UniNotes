Try-with-resources - will clear declared statements in the brackets after the block ends

#### Benefits of exceptions
- Documentation
- Type safety
- Separation of concern - main logic and exception logic are separated with the try-catch

#### Checked vs unchecked
Checked - must be handled or passed up
- Client must take a recovery action
- Java requires you to declare exceptions that your method throws
- Java requires catching the exception when the function is called
Unchecked - not expected to be handled
- Nothing the client could do
- Programming error
- Extends `RuntimeException`
- e.g. `NullPointerException`

- Never ignore an exception
- Never catch `Exception`
- Document exceptions at the API level
- Avoid implementation-specific exceptions (be more general in their names)
- Never use exceptions for control flow

#### Assertions
Check a boolean statement. If the statement is false, the code crashes.

### Design patterns
General reusable solutions to commonly occurring problems in software design

#### Open-Closed Principle
Classes should be open for extension but closed for modification

#### Composite
Lets you treat objects and groups of objects uniformly by inheriting and containing a class.
In other words, you treat objects and a container of objects the same, by implementing the operation for the box of objects class with a foreach loop.

#### Decorator
Way of adding functionality to a class, by containing and inheriting an object of that class. Delegate the inherited methods to the wrapped object

#### State
Containing an object inside another so it is changeable, e.g. an Employee contains a Rank which can be a Manager or Assistant, rather than Manager and Assistant inheriting Employee. All work is done through this Rank object.
Never allow access to the reference of this contained object!

#### Strategy
Being able to choose an algorithm at runtime

#### Singleton
Ensuring only one instance of an object is created.
`private` constructor, `static` reference to the own object stored as state. `public` method to access inside object, and creates it if it is null.