# Question

Given an integer array nums, return all the triplets [nums[i], nums[j], nums[k]] such that i != j, i != k, and j != k, and nums[i] + nums[j] + nums[k] == 0.

Notice that the solution set must not contain duplicate triplets.


##### Example:
Input: nums = [-1,0,1,2,-1,-4]

Output: [[-1,-1,2],[-1,0,1]]


# Optimal Solution

``` python
    def threeSum(self, nums):
        nums.sort()
        temp=[]
        n=len(nums)
        for i in range(n):
            if i>0 and nums[i]==nums[i-1]:
                continue
            j=i+1
            k=n-1
            while(j<k):
                sum=nums[i]+nums[j]+nums[k]
                if sum<0:
                    j+=1
                elif sum>0:
                    k-=1
                else:
                    temp.append([nums[i],nums[j],nums[k]])
                    j+=1
                    k-=1
                    while(j<k and nums[j]==nums[j-1]):
                        j+=1
                    while(j<k and nums[k]==nums[k+1]):
                        k-=1
        return temp
            
```
### Time Complexity:o(nlogn)+O(n²) approximately:O(n²)
### Space Complexity: o(no.of triplets) 
