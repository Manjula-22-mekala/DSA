





# generating all subsets


``` python
    def subsets(self, nums, index=0, ans=None, res=None):
    if ans is None:
        ans = []
    if res is None:
        res = []

    if index == len(nums):
        res.append(ans[:])
        return res

    # take
    ans.append(nums[index])
    self.subsets(nums, index + 1, ans, res)

    # not take
    ans.pop()
    self.subsets(nums, index + 1, ans, res)

    return res

```
        
# print subsets with sum==k
``` python
    def subsets(self, nums, k, index=0, ans=None, res=None):
        if ans is None:
            ans = []
        if res is None:
            res = []

        if index == len(nums):
            if sum(ans) == k:
                res.append(ans[:])
            return res

        # take
        ans.append(nums[index])
        self.subsets(nums, k, index + 1, ans, res)

        # not take
        ans.pop()
        self.subsets(nums, k, index + 1, ans, res)

        return res

            
```
# print any one subsequence with given sum
``` python
    def subsequenceSum(self, nums, target, index=0, ans=None, curr_sum=0):
        if ans is None:
            ans = []

        if index == len(nums):
            if curr_sum == target:
                print(ans)      # prints any one valid subsequence
                return True     # stop further recursion
            return False

        # take
        ans.append(nums[index])
        if self.subsequenceSum(nums, target, index + 1, ans, curr_sum + nums[index]):
            return True

        # not take
        ans.pop()
        if self.subsequenceSum(nums, target, index + 1, ans, curr_sum):
            return True

        return False
```
# subsetssum-1
``` python
    def subsetSums(self, nums):
        def func(ind, sum, nums, ans):
            if ind == len(nums):
                ans.append(sum)
                return
            func(ind + 1, sum + nums[ind], nums, ans)
            func(ind + 1, sum, nums, ans)
        
        ans = []
        func(0, 0, nums, ans)
        return ans
```
# subsetssum-2
``` python
    def subsetsWithDup(self, nums):
        nums.sort()
        ans=[]
        def subset(ind,ds):
            ans.append(ds[:])
            for i in range(ind,len(nums)):
                if i>ind and nums[i]==nums[i-1]:
                    continue
                ds.append(nums[i])
                subset(i+1,ds)
                ds.pop()
        subset(0,[])
        return ans


```
           
### Time Complexity:O(n.2^n)
### Space Complexity:O(n.2^n)
