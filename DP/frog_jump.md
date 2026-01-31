
# Question frog jump

``` python
    #1 step and 2 step s
    def frogJump(self, heights):
        #tabulation
        n=len(heights)
        dp=[-1]*n
        dp[0]=0
        for i in range(1,n):
            left=dp[i-1]+abs(heights[i]-heights[i-1])
            right=float('inf')
            if i>1:
                right=dp[i-2]+abs(heights[i]-heights[i-2])
            dp[i]=min(left,right)
        return dp[n-1]
            
    #1,2,3....k steps
    def frogJump(self, heights, k):
        n=len(heights)
        dp=[-1]*n
        dp[0]=0
        for i in range(1,n):
            minsteps=float('inf')
            for j in range(1,k+1):
                if i-j>=0:
                    jumps=dp[i-j]+abs(heights[i]-heights[i-j])
                    minsteps=min(minsteps,jumps)
            dp[i]=minsteps
        return dp[n-1]
```