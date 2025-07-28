# Question
Given two strings s and goal, return true if and only if s can become goal after some number of shifts on s.


##### Example:
Input: s = "abcde", goal = "cdeab"

Output: true

# Optimal Solution

``` python
    def rotateString(self, s, goal):
        for i in range(len(s)):
            if s[i+1:]+s[:i+1]==goal:
                return True
        return False
        
            
```
### Time Complexity:O(n)
### Space Complexity: O(1)
