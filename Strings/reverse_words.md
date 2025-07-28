# Question
Reverse words in a given string

##### Example:
Input: s = "the sky is blue"

Output: "blue is sky the"

# Optimal Solution

``` python
    def reverseWords(self, s):
        s=s.strip()
        s=s.split()
        for i in range(len(s)//2):
            s[i],s[len(s)-i-1]=s[len(s)-i-1],s[i]
        return ' '.join(s)
            
```
### Time Complexity:O(n)
### Space Complexity:O(n) 
