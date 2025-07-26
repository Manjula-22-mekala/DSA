# Question
Given a pair of strings s1 and s2 of equal lengths, your task is to find which of the two strings has more distinct subsequences. If both strings have the same number of distinct subsequences, return s1.


##### Example:
Input: s1 = "gfg", s2 = "ggg"

Output: "gfg"

Explanation: "gfg" have 6 distinct subsequences whereas "ggg" have 3 distinct subsequences. 


# Naive solution


``` python
    def betterString(self, s1, s2):
        # Code here
        def get_subsequences(s): 
            res=set()
            def ps(i,ans):
                if i>=len(s):
                    res.add("".join(ans))
                    return
                ans.append(s[i])
                ps(i+1,ans)#taking
                ans.pop()
                ps(i+1,ans)#not taking
            ps(0,[])
            return res
        set1=get_subsequences(s1)
        set2=get_subsequences(s2)
        if len(set1)>=len(set2):
            return s1
        else:
            return s2
```
### Time Complexity:O(2^n)
### Space Complexity:O(2^n)   
# Optimal
``` python
    def counti(s):
            res=1
            last=[0]*26
            n=len(s)
            for i in range(1,n+1):
                cur=2*res-last[ord(s[i-1])-ord('a')]
                last[ord(s[i-1])-ord('a')]=res
                res=cur
            return res
        a=counti(s1)
        b=counti(s2)
        return s2 if a<b else s1
            
```
### Time Complexity:O(2^n)
### Space Complexity:O(n)+O(26)
