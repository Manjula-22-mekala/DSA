# Question

Given an array of N integers and Q queries of indices. For each query indices[i], determine the count of elements in arr that are strictly greater than arr[indices[i]] to its right (after the position indices[i]).


##### Example:
Input: arr[] = [3, 4, 2, 7, 5, 8, 10, 6], queries = 2, indices[] = [0, 5]
Output:  [6, 1]
Explanation: The next greater elements to the right of 3(index 0) are 4,7,5,8,10,6. The next greater elements to the right of 8(index 5) is only 10.

# Optimal Solution


``` python
    def count_NGE(self, arr, indices):
        # Code here
        queries=len(indices)
        N=len(arr)
        res=[]
        for i in range(queries):
            res.append(self.nge(arr,indices[i],N))
        return res
    def nge(self,arr,index,N):
        cnt=0
        for i in range(index+1,N):
            if arr[i]>arr[index]:
                cnt+=1
        return cnt
```
### Time Complexity:O(n)
### Space Complexity: O(n)
