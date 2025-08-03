# Question

Given an array, find the nearest smaller element G[i] for every element A[i] in the array such that the element has an index smaller than i.


##### Example:
Input 1:
    A = [4, 5, 2, 10, 8]
Output 1:
    G = [-1, 4, -1, 2, 2]


### optimal solution
```python
    def prevSmaller(self, A):
		n=len(A)
		st=[]
		nge=[-1]*n
		for i in range(n):
			while st and st[-1]>=A[i]:
				st.pop()
			if st:
				nge[i]=st[-1]
			st.append(A[i])
		return nge

```



### Time Complexity:O(n)
### Space Complexity: O(n)
