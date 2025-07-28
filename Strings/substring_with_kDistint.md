# Question

Given a string consisting of lowercase characters and an integer k, the task is to count all possible 
substrings (not necessarily distinct) that have exactly k distinct characters. 


##### Example:
Input: s = "abc", k = 2

Output: 2

Explanation: Possible substrings are ["ab", "bc"]


### Naive solution
```python
        st=''
        cnt=0
        for i in range(len(s)):
            for j in range(i,len(s)):
                st=s[i:j+1]
                seti=set(st)
                if len(seti)==k:
                    cnt=cnt+1
        return cnt
        


```
### Time Complexity:O(n3)

# Optimal Solution


``` python
    def countSubstr(self, s, k):
        l = len(s)
        return self.subtrack(s, l, k) - self.subtrack(s, l, k - 1)

    def subtrack(self, s, l, k):
        if k == 0:
            return 0  # nothing to do
        dt = {}
        cnt = 0
        i = j = 0
        while i < l:
            while j < l and (len(dt) < k or (len(dt) == k and s[j] in dt)):
                dt[s[j]] = dt.get(s[j], 0) + 1
                j += 1
            cnt += (j - i)
            if s[i] in dt:
                dt[s[i]] -= 1
                if dt[s[i]] == 0:
                    del dt[s[i]]
            i += 1
        return cnt
            
```
### Time Complexity:O(n²)
### Space Complexity: O(n)--not using any Data structure---got rid off 
