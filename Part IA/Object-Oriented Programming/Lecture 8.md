### Java's Generics Implementation
Adding generics while retaining backwards compatibility:
1. Templates - the generic class is treated as a template by the compiler, which generates new classes from it whenever you ask for something, e.g. `ArrayList<Integer>` creates a class for `ArrayListInteger`. C++ uses this method
2. Type erasure - At compile time, do all the type checks you can, then delete the type information in the compiler output. e.g. `ArrayList<Integer>` is checked, and then written to bytecode as plain ArrayList. The JVM will never know and so dynamic checks aren't possible. This is what Java implements. Primitives **cannot** be passed in
Pros of type erasure:
- Bytecode unchanged, hence backwards compatible
- Compile time type checking reduces bugs
- Avoids bloat of templates (all those extra classes)
Cons:
- No runtime checking
- Cannot use primitive parameters - compiler replaces parameter with Object, which obviously cannot replace primitives
- Creation is tricky - compiler is unsure how to deal with new, as `new Object()` is not useful
- Method overloading is limited - type signatures will change to be the same if using generics e.g.
```java
void addAll(List<String> items) {...}
void addAll((List)<Integer> items) {...}
```
This will not work because after discarding type information the signatures are the same.

#### Covariance
If B is a subtype of A, then i should be able to use B everywhere i expect an A (Liskov substitution principle)
Java classes are covariant, and so are arrays - but this can lead to runtime errors
Arrays know their type at runtime - they are reified.

#### Wildcard
Suppose you wanted to make a function to print every item in a list regardless of type
```java
void printAll (List<?> list) {
	for (Object o : list)
		System.out.println(o);
}
```
`<? extends A>` matches anything that is type A or a subtype of it (covariance)
`List<? extends Number>` - it is safe to read Number types from this, but not to write (you cannot tell if it is Double or Integer etc)
`<? super A>` matches anything that is type A or a supertype of it (contravariance)
`List<? super Number>` - It is only safe to read Objects from this, but safe to write Number or its subclasses

#### Coupling
Degree to which different parts of a program depend on each other
High coupling - relying on internals/implementation details
Loose coupling - relying on interface and defined behaviour
High coupling is bad

#### Boxing
Java automatically converts between primitives and their corresponding object wrapper - this is autoboxing
Boxing - turn an int into an Integer
Unboxing - turn an Integer into an int
Boxed objects have more memory overhead
Auto-unboxing fails with null (null pointer exception)

#### Errors
The traditional way to handle errors is to return a value that indicates success/failure/error
However:
- Could ignore the return value
- You have to keep checking what the return values are meant to signify
- The actual result often can't be returned in the same way
- Error handling code is mixed in with normal execution - makes code harder to read and maintain
A similar idea is to set some state in the system that needs to be checked for errors (deferred error handling)

#### Exceptions
Exceptions are events which occur during the execution of a program that disrupts the normal flow of the programs instructions
In Java, this is handled with `try` and `catch`
An exception is an object that has `Exception` as an ancestor, so it needs to be created with `new` before throwing.
Multiple `catch` handlers are allowed to test different exceptions, and exceptions can be joined with `|`
`finally` runs after any handlers