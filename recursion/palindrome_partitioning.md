# Question

Given a string s, partition s such that every substring of the partition is a palindrome. Return all possible palindrome partitioning of s.

##### Example:
Input: s = "aab"
Output: [["a","a","b"],["aa","b"]]
# Optimal
``` python
    def partition(self, s):
        self.res = []
        self.path = []
        self.backtrack(0, s)
        return self.res

    def is_palindrome(self, s, left, right):
        while left <= right:
            if s[left] != s[right]:
                return False
            left += 1
            right -= 1
        return True

    def backtrack(self, index, s):
        if index == len(s):
            self.res.append(self.path[:])
            return
        for i in range(index, len(s)):
            if self.is_palindrome(s, index, i):
                self.path.append(s[index:i+1])
                self.backtrack(i+1, s)
                self.path.pop()
            
```

