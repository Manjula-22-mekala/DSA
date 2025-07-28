# Question
Given a valid parentheses string s, return the nesting depth of s. The nesting depth is the maximum number of nested parentheses.

##### Example:
Input: s = "(1+(2*3)+((8)/4))+1"

Output: 3

# Optimal Solution

``` python
    def maxDepth(self, s):
        """
        :type s: str
        :rtype: int
        """
        cnt,maxi=0,0
        for i in s:
            if i=='(':
                cnt=cnt+1
            elif i==')':
                cnt=cnt-1
            maxi=max(cnt,maxi)
        return maxi
```
### Time Complexity:O(n)
### Space Complexity:O(1) 
