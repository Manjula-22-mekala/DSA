# Question

Given an array nums of n integers, return an array of all the unique quadruplets [nums[a], nums[b], nums[c], nums[d]] such that:


##### Example:
Input: nums = [1,0,-1,0,-2,2], target = 0

Output: [[-2,-1,1,2],[-2,0,0,2],[-1,0,0,1]]


# Optimal Solution


``` python
    def fourSum(self, nums, target):
        nums.sort()
        temp=[]
        n=len(nums)
        for i in range(n):
            if i>0 and nums[i]==nums[i-1]:
                continue
            for j in range(i+1,n):
                if j>i+1 and nums[j]==nums[j-1]:
                    continue
                k,l=j+1,n-1
                while(k<l):
                    sum=nums[i]+nums[j]+nums[k]+nums[l]
                    if sum<target:
                        k+=1
                    elif sum>target:
                        l-=1
                    else:
                        temp.append([nums[i],nums[j],nums[k],nums[l]])
                        k+=1
                        l-=1
                        while (k<l and nums[k]==nums[k-1]):
                            k+=1
                        while (k<l and nums[l]==nums[l+1]):
                            l-=1
        return temp
            
```
### Time Complexity:
### sort-O(nlogn),for fixing 2 pointers with in 2 nested loops-o(n2)
### for moving 2 pointers-o(n)
### so,totally O(n³)
### Space Complexity: O(no.of triplets)
