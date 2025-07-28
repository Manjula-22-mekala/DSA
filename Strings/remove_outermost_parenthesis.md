# Question

Remove outermost parenthesis in string


##### Example:
Input: s = "(()())(())"

Output: "()()()"

# Optimal


``` python
    def removeOuterParentheses(self, s):
        res=[]
        b=0
        for char in s:
            if char=='(':
                if b>0:
                    res.append(char)
                b=b+1
            elif char==')':
                b=b-1
                if b>0:
                    res.append(char)
        return ''.join(res)
```
        
### Time Complexity:O(n)
### Space Complexity:O(n)
