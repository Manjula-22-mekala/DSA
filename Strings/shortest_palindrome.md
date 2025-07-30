# Question
You are given a string s. You can convert s to a palindrome by adding characters in front of it.

Return the shortest palindrome you can find by performing this transformation.

##### Example:
Input: s = "aacecaaa"

Output: "aaacecaaa"


# Optimal Solution


``` python
    def shortestPalindrome(self, s):
        def lps(temp):
            n=len(temp)
            lps=[0]*n
            pre,suf=0,1
            while(suf<n):
                if temp[pre]==temp[suf]:
                    lps[suf]=pre+1
                    suf+=1
                    pre+=1
                else:
                    if pre==0:
                        lps[suf]=0
                        suf+=1
                    else:
                        pre=lps[pre-1]
            return lps

        if not s:
            return s
        rev_s=s[::-1]
        temp=s+'#'+rev_s
        lps_arr=lps(temp)
        add_to=rev_s[:len(s)-lps_arr[-1]]
        return add_to+s
            
```
### Time Complexity:O(n+m)
### Space Complexity: O(1) 
