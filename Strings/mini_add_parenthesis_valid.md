# Question
A parentheses string is valid if and only if:

It is the empty string,
It can be written as AB (A concatenated with B), where A and B are valid strings, or
It can be written as (A), where A is a valid string.
You are given a parentheses string s. In one move, you can insert a parenthesis at any position of the string.

For example, if s = "()))", you can insert an opening parenthesis to be "(()))" or a closing parenthesis to be "())))".
Return the minimum number of moves required to make s valid.

##### Example:
Input: s = "())"
Output: 1

# Optimal Solution

``` python
    def minAddToMakeValid(self, s):
        """
        :type s: str
        :rtype: int
        """
        cnt1,cnt2=0,0
        for i in s:
            if i=="(":
                cnt1=cnt1+1
            elif i==')' and cnt1>0:
                cnt1=cnt1-1
            else:
                cnt2+=1
        return cnt1+cnt2
            
```
### Time Complexity:O(n)
### Space Complexity:O(1) 
