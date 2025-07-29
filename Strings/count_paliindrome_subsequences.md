# Question
Given a string s, you have to find the number of palindromic subsequences (need not necessarily be distinct) present in the string s. 

##### Example:
Input: s = "abcd"
Output: 4
Explanation: palindromic subsequence are : 'a' ,'b', 'c' ,'d'

# Optimal Solution
``` python
    def countPS(self,s):
        n = len(s)
        prev = [0] * n
        curr = [0] * n
    
        for i in range(n - 1, -1, -1):
            for j in range(i, n):
                if i == j:
                    curr[j] = 1
                elif s[i] == s[j]:
                    curr[j] = curr[j - 1] + prev[j] + 1
                else:
                    curr[j] = curr[j - 1] + prev[j] - prev[j - 1]
            prev = curr[:]
        return prev[n - 1]
            
```
### Time Complexity:O(n2)
### Space Complexity: O(1)
