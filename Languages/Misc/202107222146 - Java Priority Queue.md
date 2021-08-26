## Priority Queue

Tags: #Java #PriorityQueue
See also :
Previous :

### Body
- By default it is a min heap
 ```java
 PriorityQueue<E> pq = new PriorityQueue(int initialCapacity, 
 Comparator<E> comparator); 
 ```
 Methods: -
 - boolean **add(E element)**: This method inserts the specified element into this priority queue.
- public **peek()**: This method retrieves, but does not remove, the head of this queue, or returns null if this queue is empty.
- public **poll()**: This method retrieves and removes the head of this queue, or returns null if this queue is empty.

### References
- https://www.geeksforgeeks.org/priority-queue-class-in-java-2/