# Question

The beauty of a string is the difference in frequencies between the most frequent and least frequent characters.

For example, the beauty of "abaacc" is 3 - 1 = 2.
Given a string s, return the sum of beauty of all of its substrings.

##### Example:
Input: s = "aabcb"
Output: 5
Explanation: The substrings with non-zero beauty are ["aab","aabc","aabcb","abcb","bcb"], each with beauty equal to 1.
# Optimal Solution
``` python
     def beautySum(self, s):
        total_beauty=0
        for i in range(len(s)):
            freq={}
            for j in range(i,len(s)):
                freq[s[j]]=freq.get(s[j],0)+1
                total_beauty+=(max(freq.values())-min(freq.values()))
        return total_beauty
            
```
### Time Complexity:O(n)
### Space Complexity: O(1)
