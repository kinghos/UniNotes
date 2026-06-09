#### Iterators
Used in foreach loops. 
```java
Iterator<Integer> it = list.iterator();
while(it.hasNext()) {Integer i = it.next();}
for (; it.hasNext(); ) {Integer i = it.next();}
```
#### Queues
`offer()` to add to the back and `poll()` to get things from the front.

#### Maps
- Like dictionaries in ML
- Maps key objects to value objects
- Keys must be unique
- TreeMap - keys kept in order
- HashMap - keys not in order, but have efficient access

#### Sets
- Collection with no duplicates
- Represents mathematical notion of a set
- TreeMap - objects stored in order
- HashSet - objects in unpredictable order but fast to operate on

#### Collections methods
`Collections.unmodifiableList(list);` makes a list unmodifiable.

### Comparing
#### Value equality
- Use the `equals()` method in Object
- Default implementation is reference equality (`==`)
- Java requires that if two objects are equal their hash codes must be equal
#### Comparable
- `Comparable` interface has `compareTo` method
- Tells you which is bigger, smaller, equal, useful for sorting
- Returns an integer r - <0 is smaller, 0 is equal, >0 is larger
- `compare` can be used to specify a certain ordering

### Generics
- Aim to allow a type or method to operate on objects of various types while providing compile-time type safety
- aka parametric polymorphism
- It stops a specific type of error at compile time
- Prevents mixing of types and excessive casting
Generics can be declared like:
```java
public class Box<T> {
	private T t;
	...
}
```
where T acts as a sort of placeholder
