# Question

you are given an integer array nums. The range of a subarray of nums is the difference between the largest and smallest element in the subarray.

Return the sum of all subarray ranges of nums.

A subarray is a contiguous non-empty sequence of elements within an array.


##### Example:
Input: nums = [1,2,3]
Output: 4
Explanation: The 6 subarrays of nums are the following:
[1], range = largest - smallest = 1 - 1 = 0 
[2], range = 2 - 2 = 0
[3], range = 3 - 3 = 0
[1,2], range = 2 - 1 = 1
[2,3], range = 3 - 2 = 1
[1,2,3], range = 3 - 1 = 2
So the sum of all ranges is 0 + 0 + 0 + 1 + 1 + 2 = 4.


### optimal solution
```python
    def subArrayRanges(self, nums):
        n = len(nums)
        total = 0
        for i in range(n):
            min_val = max_val = nums[i]
            for j in range(i+1, n):
                min_val = min(min_val, nums[j])
                max_val = max(max_val, nums[j])
                total += max_val - min_val
        return total

```



### Time Complexity:O(n2)
### Space Complexity: O(1)