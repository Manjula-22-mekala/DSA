# Question

A digit string is good if the digits (0-indexed) at even indices are even and the digits at odd indices are prime (2, 3, 5, or 7).

Given an integer n, return the total number of good digit strings of length n


##### Example:

Input: n = 4

Output: 400

# Optimal Solution


``` python
        def countGoodNumbers(self, n):
        """
        :type n: int
        :rtype: int
        """
            mod=10**9 + 7
            def good(x,y):
                if y==0:
                    return 1
                if y%2==0:
                    h=good(x,y//2)
                    return (h*h)%mod
                else:
                    return (x*good(x,y-1))%mod
            even=(n+1)//2
            odd=n//2
            return (good(5,even)*good(4,odd)) % mod
```
### Time Complexity:O(logn)
### Space Complexity: O(logn)
