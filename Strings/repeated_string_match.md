# Question

Given two strings a and b, return the minimum number of times you should repeat string a so that string b is a substring of it. If it is impossible for b​​​​​​ to be a substring of a after repeating it, return -1.

Notice: string "abc" repeated 0 times is "", repeated 1 time is "abc" and repeated 2 times is "abcabc".
##### Example:

Input: a = "abcd", b = "cdabcdab"
Output: 3
Explanation: We return 3 because by repeating a three times "abcdabcdabcd", b is a substring of it.
# Optimal Solution
``` python
    def repeatedStringMatch(self, a, b):
        #there is no ceil in python, -(-x//y)==ceil(x/y)
        repeated_count=-(-len(b)//len(a))
        for i in range(3):
            if b in a*(repeated_count+i):
                return repeated_count+i
        return -1
            
```
### Time Complexity:O(3)
### Space Complexity: O(1)
