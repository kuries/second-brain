## Floyd's Cycle detection algorithm

Related to : Linked lists
See also :
Previous :

### Find if there is a loop.
- It involves using two pointers (say `p1` and `p2`) that move at different speeds, one with speed 1 and the other with speed 2. 
- If there is a cycle, the two pointers will end up pointing to the same element after a finite number of steps.

### Get to the starting point of the loop.
- Now place `p1` at the starting point of the linked list and move `p1` and `p2` with same speeds.
- If they meet again, then the meeting point is the answer.

### Why does it work?
 **1st explanation**
 
 ![[Pasted image 20210705111601.png]]
 
 Let `S` be the slower pointer and `F` the faster one.
 
 $S : m+pn+k$
 $F:  m+qn+k$ where $q>p$
 Since, the time taken is same,
 $2(m+pn+k) = m+qn+k$
 $m+k = n(q-2p)$ where $q-2p$ is an integer.
 
 Here we can say that $m+k$ is an integer multiple of the length of the loop.
 
 After we place $S$ at the start of the loop and move both of them with same speeds,
 - $S$ traverses distance $m$ to reach the start of the loop.
 - $F$ traverses a distance $m$ and combined with the offset distance $k$ from the start of the loop ($m+k$), it ends up at the start of the loop.

 **2nd explanation**

Suppose, $F$ has a headstart on $S$ by $k$ steps in a loop of size n.
Then, then are going to meet at $-k$ distance from the starting point.

__Proof__: 

$V_{F/S} = 1 , S_{F/S} = n-k$
So,
$t = (n-k)/1$
$S_{F} = k+2(n-k)$ as $s = vt$
$S_{S} = n-k$

Now, back to the problem.
- F has a headstart by m by the time S reaches the start of the loop.
- We can now turn this into our previous problem and we'll see that they both meet at a point `m` from the start of the loop.
### References
- [stackoverflow 1](https://stackoverflow.com/questions/5607292/interview-remove-loop-in-linked-list-java)
- [stackoverflow 2](https://stackoverflow.com/questions/3952805/proof-of-detecting-the-start-of-cycle-in-linked-list)
- [quora](https://www.quora.com/How-does-Floyds-cycle-finding-algorithm-work-How-does-moving-the-tortoise-to-the-beginning-of-the-linked-list-while-keeping-the-hare-at-the-meeting-place-followed-by-moving-both-one-step-at-a-time-make-them-meet-at-starting-point-of-the-cycle)
- [youtube](https://youtu.be/apIw0Opq5nk)