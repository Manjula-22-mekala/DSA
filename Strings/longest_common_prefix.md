# Question

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

##### Example:
Input: strs = ["flower","flow","flight"]
Output: "fl"

# Optimal Solution
``` python
    def longestCommonPrefix(self, strs):
        pre=strs[0]
        for i in strs[1:]:
            while not i.startswith(pre):
                pre=pre[:-1]
                if not pre:
                    return ""
        return pre
            
```
### Time Complexity:O(n)
### Space Complexity: O(1)
