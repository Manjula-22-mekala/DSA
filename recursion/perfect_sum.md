# Question

Given an array arr of non-negative integers and an integer target, the task is to count all subsets of the array whose sum is equal to the given target.


##### Example:
Input: arr[] = [2, 5, 1, 4, 3], target = 10

Output: 3

Explanation: The subsets {2, 1, 4, 3}, {5, 1, 4}, and {2, 5, 3} sum up to the target 10.


### Naive solution
```python
    def perfectSum(self, arr, target):
		# code here
	    cnt = 0 # getting time limit exceeded
        def sumpro(i, summ):
            nonlocal cnt
            if i == len(arr):
                if summ == target:
                    cnt += 1
                return
            sumpro(i + 1, summ + arr[i])  # include arr[i]
            sumpro(i + 1, summ)           # exclude arr[i]

        sumpro(0, 0)
        return cnt

```

# Therefore Time complexity=O(2^n)
# Space complexity=O(n)


# using functools lru_cache


``` python
    from functools import lru_cache
    @lru_cache(None)
    def countSubsets(i, currentSum):
        if i == len(arr):
            return 1 if currentSum == target else 0
    
        # include arr[i]
        take = countSubsets(i + 1, currentSum + arr[i])
        # exclude arr[i]
        not_take = countSubsets(i + 1, currentSum)
        return take + not_take
    
    return countSubsets(0, 0)
            
```
### Time Complexity:O(2^n)
### Space Complexity: O(n)
