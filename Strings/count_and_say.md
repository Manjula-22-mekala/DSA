# Question

The count-and-say sequence is a sequence of digit strings defined by the recursive formula:

countAndSay(1) = "1"
countAndSay(n) is the run-length encoding of countAndSay(n - 1).
Run-length encoding (RLE) is a string compression method that works by replacing consecutive identical characters (repeated 2 or more times) with the concatenation of the character and the number marking the count of the characters (length of the run). For example, to compress the string "3322251" we replace "33" with "23", replace "222" with "32", replace "5" with "15" and replace "1" with "11". Thus the compressed string becomes "23321511".

Given a positive integer n, return the nth element of the count-and-say sequence. 


##### Example:
Input: n = 4

Output: "1211"

Explanation:

countAndSay(1) = "1"
countAndSay(2) = RLE of "1" = "11"
countAndSay(3) = RLE of "11" = "21"
countAndSay(4) = RLE of "21" = "1211"


# Optimal Solution


``` python
    def countAndSay(self, n):
        """
        :type n: int
        :rtype: str
        """
        res='1'
        for _ in range(1,n):
            res=self.build_next(res)
        return res
    def build_next(self,s):
        cnt=1
        result=''
        for i in range(1,len(s)):
            if s[i]==s[i-1]:
                cnt+=1
            else:
                result+=str(cnt)+s[i-1]
                cnt=1
        result+=str(cnt)+s[-1]
        return result
            
```
### Time Complexity:O(n)
### Space Complexity: O(1) 
