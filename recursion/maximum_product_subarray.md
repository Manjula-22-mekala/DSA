# Question

Given an integer array nums, find a subarray that has the largest product, and return the product.


##### Example:
Input: nums = [2,3,-2,4]

Output: 6

Explanation: [2,3] has the largest product 6.


### optimal solution
```python
    def maxProduct(self, nums):
        pre,suf=1,1
        ans=float('-inf')
        n=len(nums)
        for i in range(n):
            if pre==0:
                pre=1
            if suf==0:
                suf=1
            pre=pre*nums[i]
            suf=suf*nums[n-i-1]
            ans=max(ans,max(pre,suf))
        return ans

```
### Time Complexity:O(n)
### Space Complexity: O(1)--not using any Data structure---got rid off 

