
# Question combination 1

``` python
    def combinationSum(self, candidates, target):
        """
        :type candidates: List[int]
        :type target: int
        :rtype: List[List[int]]
        """
        ans=[]
        def findcombinations(ind,target,ds):
            if ind==len(candidates):
                if target==0:
                    ans.append(ds[:])
                return
            
            if candidates[i]<=target:
                ds.append(candidates[ind])
                findcombinations(ind,target-candidates[i],ds)
                ds.pop()
            
            findcombinations(ind+1,target,ds)
        findcombinations(0,target,[])
        return ans
            
```

# combination 2
``` python
def combinationSum2(self, candidates, target):
        """
        :type candidates: List[int]
        :type target: int
        :rtype: List[List[int]]
        """
        candidates.sort()
        ans=[]
        def findcombinations(ind,target,ds):
            if target==0:
                ans.append(ds[:])
                return
            
            for i in range(ind,len(candidates)):
                if i>ind and candidates[i]==candidates[i-1]:
                    continue
                if candidates[i]>target:
                    break
                ds.append(candidates[i])
                findcombinations(i+1,target-candidates[i],ds)
                ds.pop()
        findcombinations(0,target,[])
        return ans
```     

