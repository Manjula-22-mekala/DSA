# Question
Given a positive integer n, count the number of digits in n that divide n evenly (i.e., without leaving a remainder). Return the total number of such digits.

A digit d of n divides n evenly if the remainder when n is divided by d is 0 (n % d == 0).
Digits of n should be checked individually. If a digit is 0, it should be ignored because division by 0 is undefined.


##### Example:
Input: n = 12

Output: 2

Explanation: 1, 2 when both divide 12 leaves remainder 0.
# Optimal Solution

``` python
        def evenlyDivides(self, n):
        # code here
            temp=n
            cnt=0
            digit=0
            while n>0:
                digit=n%10
                if digit!=0:
                    if temp%digit==0:
                        cnt=cnt+1
                    
                n=n//10
            return cnt
```
### Time Complexity:O(logn)
### Space Complexity: O(1)
