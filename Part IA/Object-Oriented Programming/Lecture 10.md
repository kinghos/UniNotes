#### Observer
Way of identifying when an object changes state. Works by having a method in the "subject" to attach/detach any observers. Then, a `notify()` method can be called to update the state of all observers to reflect the change of state in the subject.

### Lambdas
You can declare anonymous classes.
```java
List<Apple> result = filter(inventory,
	new ApplePredicate() {
		public boolean test(Apple apple) {
			return "red".equals(apple.getColor());
		}
	}
);
```
This can be reduced further down to an anonymous method, i.e. a lambda function
```java
List<Apple> result = filter(inventory,
	(Apple apple) -> "red".equals(apple.getColour()));
```
In this example, the second argument to filter is an `ApplePredicate`. Despite not being explicitly stated, the compiler can detect that `ApplePredicate` has only one method, `test`, and that it must be the function to call. This is called a functional interface.
```java
(parameters) -> expression
// or
(parameters) -> {statements;}
```
Generics can be used to parametrise the filter function and make it more generally useful.

#### Method references
Reuse existing method definitions and pass them like lambdas
e.g. `(Apple a) -> a.getWeight()` becomes `Apple::getWeight`

### Streams
A stream is a sequence of elements from a source that supports aggregate operations
Intermediate operations return a stream and can be connected
Terminal operations return a non-stream value