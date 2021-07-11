#### Initializing Lists
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

#### Collections.sort(List, Comparator)
- This method expects the List object to implement the **comparable** interface and override the compareTo method.
- compareTo method return neg, zero, pos numbers.
- If compareTo returns 
	- Negative - No swap
	- Zero - No swap
	- Positive - Swap

If the object does not implement the **comparable** interface there is an alternative, we can create an anonymous class which implements the comparator interface.
Ex: - (lambda)
```java
//descending order
Collections.sort(dummy, (o1, o2) -> {
            return o2.getValue()-o1.getValue();
			});

//ascending order
Collections.sort(dummy, (o1, o2) -> {
            return o1.getValue()-o2.getValue();
			});
```

(Anonymous inner class)
```java
//ascending order
Comparator<T> cmp = new Comparator<T>(){
	public int compare(T o1, T o2){
		if(o1.getVal() > o2.getVal())
			return 1;
		else
			return -1;
	}
	Collections.sort(dumy, cmp);
}
```

##### References
- [stackoverflow](https://stackoverflow.com/questions/109383/sort-a-mapkey-value-by-values)