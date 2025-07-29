# Question
Given two strings needle and haystack, return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

##### Example:
Input: haystack = "sadbutsad", needle = "sad"
Output: 0
Explanation: "sad" occurs at index 0 and 6.
The first occurrence is at index 0, so we return 0.

# Optimal Solution

``` python
    def strStr(self, haystack, needle):
        for i in range(len(haystack)):
            if haystack[i:i+len(needle)]==needle:
                return i
        return -1
            
```
### Time Complexity:O(len(haystack))
### Space Complexity:O(3) 
