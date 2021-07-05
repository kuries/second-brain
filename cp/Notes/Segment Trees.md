## Segment Trees

Related to :
See also : [[Binary Indexed Tree | BIT]]
Previous : [[202107052127 - Segment trees | Quick Summary]]

### Summary 
- We create an array of size $4*n$ and start the root at 1st index.

```cpp
int n;
int t[4*n];
```

**Code to construct the tree**

```cpp
void build(int a[], int v, int tl, int tr) {
    if (tl == tr) {
        t[v] = a[tl];
    } else {
        int tm = (tl + tr) / 2;
        build(a, v*2, tl, tm);
        build(a, v*2+1, tm+1, tr);
        t[v] = t[v*2] + t[v*2+1];
    }
}
```

**Code  to find the sum of a range**

```cpp
int sum(int v, int tl, int tr, int l, int r) {
    if (l > r) 
        return 0;
    if (l == tl && r == tr) {
        return t[v];
    }
    int tm = (tl + tr) / 2;
    return sum(v*2, tl, tm, l, min(r, tm))
           + sum(v*2+1, tm+1, tr, max(l, tm+1), r);
}
```

**Code to update a value**

```cpp
void update(int v, int tl, int tr, int pos, int new_val) {
    if (tl == tr) {
        t[v] = new_val;
    } else {
        int tm = (tl + tr) / 2;
        if (pos <= tm)
            update(v*2, tl, tm, pos, new_val);
        else
            update(v*2+1, tm+1, tr, pos, new_val);
        t[v] = t[v*2] + t[v*2+1];
    }
}
```

### Detailed Explanation

We compute and store the sum of the segment $A[0…n−1]$.

We then split the array into two halves a[0…n/2] and $a[n/2+1…n−1]$ and compute the sum of each halve and store them. 

Each of these two halves in turn also split in half, their sums are computed and stored. And this process repeats until all segments reach size 1

#### Constructing a tree

Before constructing a sum segment tree, here are a few points to note:
- Each node stores the sum of elements from range [l, r].
- To simplify the operation, each node is a sum of its two children.  Ex:- $A[l1...r2] = A[l1...r1] + A[l2...r2]$.
- Each leafnode is just a single element of the original array.

We are going to build the tree from the bottom (leaves) and keep on merging at their parents until we reach the root node.

**Ex: **
$A = [1, 3, 2, -8, 7]$ 
![[Pasted image 20210705224025.png]]

#### Sum Query 
An input $l, r$ is sent into the function to get the raange sum.

Let us assume we are at a particular node that covers the segment $A[tl...tr]$. There are 3 scenarios:

i) $l==t_{l}$ and $r==t_{r}$
- This can be handled with a simple if conditional and a return statement.

ii) $t_{l} \le l \le r \le t_{m}$ or $t_{m+1} \le l \le r \le t_{r}$
- In this case we can just go the child which completely covers the query segment.

iii) $t_{l} \le l \le t_{m}$  and $t_{m+1} \le r \le t_{r}$ 
- In this case there's no choice but to search in both the children.

**Ex: -**
Compute $\sum^{4}_{i=2}A[i]$
Sum(1, 0, 4, 2, 4)

![[Pasted image 20210705224058.png]]

#### Update Query
The update function follows the same approach to that of binary search.
After finding the element in the tree, it updates the value and while returning to the previous stacks it recomputes the sum value similar to the build query.

**Ex: -**
Update $A[2] = 3$
![[Pasted image 20210705224135.png]]

### References

- [cp-algorithms](https://cp-algorithms.com/data_structures/segment_tree.html)