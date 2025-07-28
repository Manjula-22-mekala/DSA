# Question

check 2 strings are anagram to each other or not.

anagram=formed by combination of all letters in string in any order


##### Example:
Input: s = "anagram", t = "nagaram"

Output: true

# Optimal Solution
``` python
    def isAnagram(self, s, t):
        if sorted(s)==sorted(t):
            return True
        else:
            return False
            
```
### Time Complexity:O(nlogn)
### Space Complexity: O(n)
