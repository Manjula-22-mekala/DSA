# Question

Given two integers dividend and divisor, divide two integers without using multiplication, division, and mod operator.


##### Example:
Input: dividend = 7, divisor = -3
Output: -2
Explanation: 7/-3 = -2.33333.. which is truncated to -2.


### optimal solution
```python
    def divide(self, dividend, divisor):
        if dividend==divisor:
            return 1
        sign =1
        if dividend>=0 and divisor<0:
            sign=False
        if dividend<=0 and divisor>0:
            sign=False
        n=abs(dividend)
        d=abs(divisor)
        ans=0
        while n>=d:
            cnt=0
            while(n>=(d<<(cnt+1))):
                cnt+=1
            ans+=(1<<cnt)
            n=n-(d<<(cnt))
        if ans>=2**31-1 and sign==True:
            return 2**31-1
        if ans>=2**31 and sign==False:
            return -2**31
        return ans if sign else -1*ans

```
### Time Complexity:O(log2N)**2
### Space Complexity: O(quotient)--not using any Data structure---got rid off 

