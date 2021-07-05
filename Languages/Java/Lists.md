### Initializing Lists
- `Arrays.asList` returns a mutable list while the list returned by `List.of` is immutable.
```java
List<Integer> list = Arrays.asList(1, 2, null);
list.set(1, 10); // OK

List<Integer> list = List.of(1, 2, 3);
list.set(1, 10); // Fails with UnsupportedOperationException
```
- `Arrays.asList` returns a view of the passed array, so the changes to the array will be reflected in the list too. For `List.of` this is not true.
```java
Integer[] array = {1,2,3};
List<Integer> list = Arrays.asList(array);
array[1] = 10;
System.out.println(list); // Prints [1, 10, 3]

Integer[] array = {1,2,3};
List<Integer> list = List.of(array);
array[1] = 10;
System.out.println(list); // Prints [1, 2, 3]
```
- For more info refer to [stackoverflow](https://stackoverflow.com/questions/46579074/what-is-the-difference-between-list-of-and-arrays-aslist#:~:text=Only%20this%20list%20is%20a,have%20a%20restriction%20on%20set%20.&text=Similarly%2C%20changing%20the%20backing%20array,it)