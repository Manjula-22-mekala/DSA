# Question
Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-231, 231 - 1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).
##### Example:
Input: x = -123
Output: -321

# Optimal Solution

``` python
    def reverse(self, x):
        temp=x
        rev=0
        x=abs(x)
        while(x>0):
            ldigit=x%10
            x=x//10
            rev=(rev*10)+ldigit
        rev=rev if temp>0 else -1*rev
        if rev < -2**31 or rev > 2**31 - 1:
            return 0
        return rev
```
### Time Complexity:O(logn)
### Space Complexity: O(1)
