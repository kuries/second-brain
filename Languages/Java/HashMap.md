#### Traversal
```java
//fill up x accordingly
for(Map.Entry<T1, T2> it: hashmap.entrySet()){
	System.out.printf("%x: %x", it.getKey(), it.getValue());
}
```

#### HashMap to List
```java
List<Map.Entry<String, Integer>> dummy = new ArrayList<>(hashmap.entrySet());
```