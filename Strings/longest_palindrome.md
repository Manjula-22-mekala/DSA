# Question
Given a string s which consists of lowercase or uppercase letters, return the length of the longest palindrome that can be built with those letters.

Letters are case sensitive, for example, "Aa" is not considered a palindrome.

##### Example:
Input: s = "abccccdd"
Output: 7
Explanation: One longest palindrome that can be built is "dccaccd", whose length is 7.
# Optimal Solution

``` python
    def longestPalindrome(self, s):
        """
        :type s: str
        :rtype: int
        """
        lower=[0]*26
        upper=[0]*26
        for i in s:
            if 'a'<=i<='z':
                lower[ord(i)-ord('a')]+=1
            elif 'A'<=i<='Z':
                upper[ord(i)-ord('A')]+=1
        cnt=0
        odd=0
        for i in range(26):
            if lower[i]%2==0:
                cnt=cnt+lower[i]
            else:
                cnt+=lower[i]-1
                odd=1
        for i in range(26):
            if upper[i]%2==0:
                cnt=cnt+upper[i]
            else:
                cnt+=upper[i]-1
                odd=1
        return cnt+odd
            
```
### Time Complexity:O(n)
### Space Complexity:O(1) 
