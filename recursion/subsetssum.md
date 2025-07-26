# Question----solve cheyaliii

Given an array of positive integers arr[] and a value sum, determine if there is a subset of arr[] with sum equal to given sum. 


##### Example:
Input: arr[] = [3, 34, 4, 12, 5, 2], sum = 9

Output: true 

Explanation: Here there exists a subset with target sum = 9, 4+3+2 = 9.
       
# Optimal---incomplete 
``` python
    def isSubsetSum (self, arr, sum):
        # code here 
        arr=tuple(arr)
        n=len(arr)
    
        @lru_cache(None)
        def countSubsets(i, currentSum):
            if i == n:
                return True if currentSum == sum else False
    
            # include arr[i]
            if countSubsets(i + 1, currentSum + arr[i]):
                return True
            # exclude arr[i]
            if countSubsets(i + 1, currentSum):
                return True
            else:
                return False
        return countSubsets(0, 0) # Convert tuples back to lists
            
```
### Time Complexity:O(n.2^n)
### Space Complexity:O(n.2^n)
