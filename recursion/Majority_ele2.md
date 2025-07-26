# Question

Given an integer array of size n, find all elements that appear more than ⌊ n/3 ⌋ times.


##### Example:
Input: nums = [3,2,3]

Output: [3]


### Better approach-accepted

```python
   def majorityElement(self, nums):
        l=[]
        mapp={}
        n=len(nums)
        for i in range(0,n):
            mapp[nums[i]]=mapp.get(nums[i],0)+1
            if mapp[nums[i]]==((n//3)+1):
                l.append(nums[i])
            if len(l)==2:
                break
        return l

```
### Time Complexity:O(nlogn)
### Space Complexity: O(n)


# Optimal Solution


``` python
    def majorityElement(self, nums):
        cnt1=0
        cnt2=0
        ele1=float('-inf')
        ele2=float('-inf')
        for i in range(0,len(nums)):
            if cnt1==0 and nums[i]!=ele2:
                cnt1=1
                ele1=nums[i]
            elif cnt2==0 and nums[i]!=ele1:
                cnt2=1
                ele2=nums[i]
            elif ele1==nums[i]:
                cnt1+=1
            elif ele2==nums[i]:
                cnt2+=1
            else:
                cnt1-=1
                cnt2-=1
        ls=[]
        cnt1=0
        cnt2=0
        for i in range(0,len(nums)):
            if ele1==nums[i]:
                cnt1+=1
            elif ele2==nums[i]:
                cnt2+=1
        mini=(len(nums)//3)+1
        if cnt1>=mini:
            ls.append(ele1)
        if cnt2>=mini:
            ls.append(ele2)
        return sorted(ls)
            
```
### Time Complexity:O(2n)
### Space Complexity: O(1)--not using any Data structure---got rid off 
