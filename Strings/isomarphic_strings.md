# Question
Given two strings s and t, determine if they are isomorphic.

Two strings s and t are isomorphic if the characters in s can be replaced to get t.

All occurrences of a character must be replaced with another character while preserving the order of characters. No two characters may map to the same character, but a character may map to itself.

##### Example:
nput: s = "egg", t = "add"

Output: true

Explanation:

The strings s and t can be made identical by:

Mapping 'e' to 'a'.
Mapping 'g' to 'd'.

# Optimal Solution

``` python
    def isIsomorphic(self, s, t):
        s_to_t={}
        t_to_s={}
        for i,j in zip(s,t):
            if i in s_to_t and s_to_t[i]!=j:
                return False
            if j in t_to_s and t_to_s[j]!=i:
                return False
            s_to_t[i]=j
            t_to_s[j]=i
        return True
            
```
### Time Complexity:O(n)
### Space Complexity:O(n) 
