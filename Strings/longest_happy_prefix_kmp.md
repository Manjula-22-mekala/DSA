# Question
A string is called a happy prefix if is a non-empty prefix which is also a suffix (excluding itself).

Given a string s, return the longest happy prefix of s. Return an empty string "" if no such prefix exists.


##### Example:
Input: s = "level"
Output: "l"
Explanation: s contains 4 prefix excluding itself ("l", "le", "lev", "leve"), and suffix ("l", "el", "vel", "evel"). The largest prefix which is also suffix is given by "l".


# Optimal Solution


``` python
    def longestPrefix(self, s):
        def lps(s):
            n=len(s)
            pre,suf=0,1
            lps_arr=[0]*n
            while(suf<n):
                if s[pre]==s[suf]:
                    lps_arr[suf]=pre+1
                    suf+=1
                    pre+=1
                else:
                    if pre==0:
                        lps_arr[suf]=0
                        suf+=1
                    else:
                        pre=lps_arr[pre-1]
            return lps_arr
        lps_a=lps(s)
        return s[:lps_a[-1]]
            
```
### Time Complexity:O(n)
### Space Complexity: O(1) 
