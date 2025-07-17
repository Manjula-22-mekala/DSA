# Question

Implementing pow(x, n), which calculates x raised to the power n (i.e., xn).


##### Example:
Input: x = 2.00000, n = -2

Output: 0.25000

Explanation: 2-2 = 1/22 = 1/4 = 0.25

# Optimal Solution


``` python
        def myPow(self, x, n):
            if n==0:
                return 1
            if n<0:
                return 1/self.myPow(x,-n)
            if n%2==0:
                return self.myPow(x*x,n//2)
            else:
                return x*self.myPow(x,n-1)
```
### Time Complexity:O(logn)
### Space Complexity: O(logn)
