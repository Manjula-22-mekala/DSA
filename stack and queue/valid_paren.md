``` python
def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        st=[]
        for i in s:
            if i=='(' or i=='{' or i=='[' :
                st.append(i)
            else:
                if len(st)==0:
                    return False
                else:
                    ch=st[-1]
                    st.pop()
                    if ch=='(' and i==')' or ch=='[' and i==']' or ch=='{' and i=='}':
                        continue
                    else:
                        return False
        return len(st)==0
```
