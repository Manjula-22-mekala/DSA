# Question
Given an integer array nums, return the number of reverse pairs in the array.

A reverse pair is a pair (i, j) where:


##### Example:
Input: nums = [1,3,2,3,1]

Output: 2

Explanation: The reverse pairs are:
(1, 4) --> nums[1] = 3, nums[4] = 1, 3 > 2 * 1
(3, 4) --> nums[3] = 3, nums[4] = 1, 3 > 2 * 1


# Optimal Solution


``` python
    def reversePairs(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        n=len(nums)
        return self.merge_sort(nums,0,n-1)
    def merge(self,nums,low,mid,high):
        temp=[]
        left=low
        right=mid+1
        while(left<=mid and right<=high):
            if (nums[left]<=nums[right]):
                temp.append(nums[left])
                left+=1
            else:
                temp.append(nums[right])
                right+=1
        while(left<=mid):
            temp.append(nums[left])
            left+=1
        while (right<=high):
            temp.append(nums[right])
            right+=1
        for i in range(low,high+1):
            nums[i]=temp[i-low]
    
    def counting_pairs(self,nums,low,mid,high):
        right=mid+1
        cnt=0
        for i in range(low,mid+1):
            while right<=high and nums[i]>(2*nums[right]):
                right+=1
            cnt+=(right-(mid+1))
        return cnt
            
    def merge_sort(self,nums,low,high):
        cnt=0
        if low>=high:
            return cnt
        mid=(low+high)//2
        cnt+=self.merge_sort(nums,low,mid)
        cnt+=self.merge_sort(nums,mid+1,high)
        cnt+=self.counting_pairs(nums,low,mid,high)
        self.merge(nums,low,mid,high)
        return cnt
            
```
### Time Complexity:O(n log n)
### Space Complexity: O(n)
