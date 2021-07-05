### Binary Indexed Tree

Related to :
See also : [[Segment Trees]]
Previous : [[202107051159 - Binary Indexed Tree | Quick Summary]]

### Summary
- We use an array with starting index as 1 for the sake of convenience.
- While declaring, declare an n+1 size array and initialize the array with update method for each element.
- 0th element is 0
- rangeSum(from, to) = sum(to) - sum(from-1)

**Code for Sum**: 	 
```python
def sum(arr, index):
	result=0
	while index:
		result += arr[index]
		index -= (index)&(-index)
	return result
```

**Code for Update**:
```python
def update(arr, index, val):
	while index<len(arr):
		arr[index] += val
		index = (index)&(-index)
```

### Detailed Explanation

 ![[Pasted image 20210705125921.png]]
 
 ![[Pasted image 20210705130053.png]]

### References
- [youtube](https://youtu.be/v_wj_mOAlig)