# Question
Given a string s, return the longest palindromic substring in s.

##### Example:
Input: s = "babad"
Output: "bab"
Explanation: "aba" is also a valid answer.

# Optimal Solution

``` python
    def longestPalindrome(self, s):
        ans=''
        for i in range(len(s)):
            temp1=self.expand(s,i,i)
            temp2=self.expand(s,i,i+1)
            ans=max(ans,temp1,temp2,key=len)
        return ans
    def expand(self,s,i,j):
        while i>=0 and j<len(s) and s[i]==s[j]:
            i-=1
            j+=1
        return s[i+1:j]
            
```
### Time Complexity:O(n2)
### Space Complexity:O(1) 
