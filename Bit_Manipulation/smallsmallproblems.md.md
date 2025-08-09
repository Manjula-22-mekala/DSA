# Question

Given an integer n, return true if it is a power of two. Otherwise, return false.

An integer n is a power of two, if there exists an integer x such that n == 2x.


##### Example:
Input: n = 16
Output: true
Explanation: 24 = 16

# Optimal Solution

``` python
    def isPowerOfTwo(self, n):
        if n >0 and n & n-1 == 0:
            return True
        else:
            return False
        
            
```
# Question
    odd or not
# Optimal Solution
``` python
def isEven (self, n):
        # code here 
        if n & 1==1:
            return False
        else:
            return True # even
        
```
# Question
    Check kth bit set or not
# Optimal Solution
``` python
def checkKthBit(self, n, k):
        # code here
        if (n & (1<<k))!=0:
            return True
        else:
            return False
        
```
# Question
    Check kth bit set or not
# Optimal Solution
``` python
def checkKthBit(self, n, k):
        # code here
        if (n & (1<<k))!=0:
            return True
        else:
            return False
        
```
