# Question

Given an integer array nums of unique elements, return all possible subsets (the power set).
The solution set must not contain duplicate subsets. Return the solution in any order.


##### Example:
Input: nums = [1,2,3]

Output: [[],[1],[2],[1,2],[3],[1,3],[2,3],[1,2,3]]


# Optimal-sol without using set


``` python
    def subsets(self, nums):
        """
        :type nums: List[int]
        :rtype: List[List[int]]
        """
        def sets(index,nums,ans,res):
            n=len(nums)
            if index>=n:
                res.append(ans[:])
                return
            ans.append(nums[index])
            sets(index+1,nums,ans,res) # taking
            ans.pop()
            sets(index+1,nums,ans,res)# not taking
        ans=[]
        res=[]
        sets(0,nums,ans,res)
        return res
```
        
# Optimal-sol with using set
``` python
    def subsets(self, nums):
        def sets(index, nums, ans, res):
            if index >= len(nums):
                res.add(tuple(ans))  # Convert list to tuple for set
                return
            ans.append(nums[index])       # Include nums[index]
            sets(index + 1, nums, ans, res)
            ans.pop()                     # Backtrack
            sets(index + 1, nums, ans, res)  # Exclude nums[index]

        nums.sort()  # Important to sort to handle duplicates properly
        ans = []
        res = set()
        sets(0, nums, ans, res)
        return [list(t) for t in res]  # Convert tuples back to lists
            
```
### Time Complexity:O(n.2^n)
### Space Complexity:O(n.2^n)
