# Question
Given a positive integer n, The task is to find the value of Σi F(i) where i is from 1 to n and function F(i) is defined as the sum of all divisors of i.
##### Example:
Input: n = 4
Output: 15
Explanation:
F(1) = 1
F(2) = 1 + 2 = 3
F(3) = 1 + 3 = 4
F(4) = 1 + 2 + 4 = 7
So, F(1) + F(2) + F(3) + F(4)
    = 1 + 3 + 4 + 7 = 15
# Optimal Solution
``` python
    import math
    class Solution:
        def sumOfDivisors(self, n):
            #code here
            s=0
            for i in range(1,n+1):
                s=s+self.divisiors(i)
            return s
            
        def divisiors(self,n):
            l=[]
            m=int(math.sqrt(n))
            for i in range(1,m+1):
                if n%i==0:
                    l.append(i)
                    if n//i!=i:
                        l.append(n//i)
            return sum(l)
        
```
### Time Complexity:O(logn)
### Space Complexity: O(1)
