
# Question HouseRobber1-- adjacent only

``` python 
    #tabulation
    def rob(self, nums):
        n=len(nums)
        dp=[-1]*n
        dp[0]=nums[0]

        for i in range(1,n):
            take=nums[i]
            if i-2>=0:
                take+=dp[i-2]
            nottake=dp[i-1]
            dp[i]=max(take,nottake)
        return dp[n-1]

            
```
# house robber 2 --adjacent+circular
``` python
    def rob(self, nums):
        n=len(nums)
        if n==1:
            return nums[0]
        temp1=nums[1:]
        temp2=nums[:-1]
    
        ans1=self.nonadjacent(temp1)
        ans2=self.nonadjacent(temp2)
        return max(ans1,ans2)
        
    def nonadjacent(self, nums):
        n=len(nums)
        dp=[-1]*n
        dp[0]=nums[0]

        for i in range(1,n):
            take=nums[i]
            if i-2>=0:
                take+=dp[i-2]
            nottake=dp[i-1]
            dp[i]=max(take,nottake)
        return dp[n-1]

            
```