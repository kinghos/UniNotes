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
#### Primitives
