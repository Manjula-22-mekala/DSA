# Question

Given an array arr[] of length n and an integer target, the task is to find the number of subsets with a sum equal to target.


##### Example:
Input: arr[] = [1, 2, 3, 3], target = 6 

Output: 3 

Explanation: All the possible subsets are [1, 2, 3], [1, 2, 3] and [3, 3]

        
# Optimal
``` python

def countSubsets(i, currentSum, target, arr):
    n = len(arr)

    if i == n:
        return 1 if currentSum == target else 0
    exclude = countSubsets(i + 1, currentSum, target, arr)
    include = 0
    if arr[i] + currentSum <= target:
        include = countSubsets(i + 1, currentSum + arr[i], target, arr)
    return include + exclude

def perfectSum(arr, target):
    return countSubsets(0, 0, target, arr)

arr = [1, 2, 3, 3]
target = 6
print(perfectSum(arr, target))
            
```
### Time Complexity:O(2^n)
### Space Complexity:O(n)
